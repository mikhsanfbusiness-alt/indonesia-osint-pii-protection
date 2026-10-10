# Indonesia PII Criticality Ranking (IPCR)

## Purpose and scope

The Indonesia PII Criticality Ranking (IPCR) is a proposed internal framework for ranking the **inherent criticality of a data category or dataset** so an organization can choose proportionate safeguards.

IPCR answers:

> **If this data were mishandled, disclosed, or misused, how serious could the harm be given the data's sensitivity and context?**

IPCR does **not** measure whether a breach is occurring, whether a system is exposed today, how many records are currently reachable, or whether existing security controls are effective. Assess those questions separately using the [Exposure Risk Model](exposure-risk-model.md).

**IPCR is not an official Indonesian government classification, a legal category, or legal advice.** Use it alongside applicable law, sector-specific requirements, contracts, and an organization's approved risk methodology.

## Ranking levels

| Level | Score | Meaning | Typical handling expectation |
|---|---:|---|---|
| **P1 — Critical** | 80–100 | Mishandling could plausibly cause severe harm, direct compromise, or high-impact abuse, especially in sensitive combinations or vulnerable contexts. | Strictly restricted access; strong encryption; robust logging; minimize copies and retention; documented response plan. |
| **P2 — Very High** | 65–79 | Data could materially enable identity fraud, significant privacy harm, financial abuse, or targeted exploitation. | Need-to-know access; encryption; masking in routine views; tightly controlled exports; access reviews. |
| **P3 — High** | 45–64 | Data could enable targeted scams, profiling, or meaningful personal harm, particularly when linked with other information. | Role-based access; secure transfer and storage; retention limits; monitored exports. |
| **P4 — Moderate** | 25–44 | Standalone data may have a more limited impact, but context and linkage can increase its significance. | Standard controlled access; avoid unnecessary publication; review combinations and bulk use. |
| **P5 — Low** | 20–24 | Limited impact in the assessed context, often because information is intentionally public or has little identifying value alone. | Maintain basic safeguards; verify intended publication and reassess if context changes. |

The minimum score is 20 because four factors are each rated from 1 to 5. The ranking is a starting point—not an automatic legal classification or a promise that every instance of a field has the same risk.

## Data criticality factors

Score each factor from 1 (low) to 5 (very high) using the rationale in [`scoring-methodology.md`](scoring-methodology.md).

| Factor | Weight | What it means |
|---|---:|---|
| Sensitivity (`S`) | 6 | Intrinsic sensitivity of the data in the assessed context. |
| Potential harm (`H`) | 6 | Severity of plausible harm if the data is mishandled or misused; do not score the likelihood of an incident here. |
| Linkability (`L`) | 4 | How readily the data can identify, single out, or profile a person when considered with relevant information. |
| Vulnerability/context (`V`) | 4 | Whether the subject population or context amplifies harm, for example children, dependent people, or safety-sensitive circumstances. |

**Formula:**

`IPCR = (S × 6) + (H × 6) + (L × 4) + (V × 4)`

Minimum: **20**. Maximum: **100**.

## Indonesian data examples — initial guidance only

These are contextual starting points, not automatic or legally binding classifications. Score the actual fields, completeness, purpose, linkability, and potential harm.

| Data category | Starting consideration | Factors that can increase criticality |
|---|---|---|
| Active passwords, session tokens, API keys, private keys | Treat active secrets as critical security assets; use the P1 floor where compromise enables meaningful access. Secrets are not necessarily PII, but still require strong protection. | Privileged access, production use, broad permissions, reusable credentials. |
| NIK/KTP, KK number, identity document images | Often P2 or higher depending on completeness and context. | Combined with name, address, signature, date of birth, tax or financial data; bulk records; vulnerable subjects. |
| Health, biometric, or genetic data | Often P2 or P1 depending on detail and consequences. | Highly detailed records, irreversible biometric exposure, discrimination or safety implications, identity linkage. |
| Bank details, financial records, payment information | Context-dependent; often P2 or higher when actionable or richly detailed. | Credentials, authentication data, transactions, balances, linked identity records. |
| NPWP and tax documents | Often P2–P3 depending on completeness and context. | Identity documents, financial details, signatures, company authorization data. |
| BPJS/KPJ, employment and payroll records | Often P2–P3 depending on fields. | Health details, salary, bank details, government identifiers, vulnerable subjects. |
| Phone number, personal email, home address | Often P3–P4 alone, depending on context. | Linked identity records, safety risks, account recovery details, mass datasets. |
| Vehicle plate (nopol) | Context-dependent; often P4 alone. | Linked owner identity, home/work locations, STNK/BPKB images, location patterns. |
| NIM/NISN, NIP, internal employee ID | Context-dependent; often P3–P4. | Children, linked academic/employment records, authentication use, detailed profiles. |
| Public company contact mailbox or published role | May be P5 in its intended public context. | Internal routing details, unintentional disclosure, linkage to non-public personal information. |

## Classification principles

1. **Classify in context, not by field name alone.** A standalone plate number is not equivalent to a plate linked to an owner's identity and home address.
2. **Keep current safeguards out of IPCR.** Strong encryption or limited access can lower current exposure risk, but should not make inherently sensitive data appear less critical.
3. **Keep exposure scale out of IPCR.** Record counts and the number of records plausibly exposed belong in the exposure-risk assessment. A large dataset may still require strong controls even when no exposure is known.
4. **Consider combinations.** Multiple individually modest fields can form a high-criticality profile when combined.
5. **Use overrides carefully.** A clear condition such as exposed active credentials can trigger a minimum handling requirement regardless of the arithmetic score. Document the reason.
6. **Record uncertainty and review dates.** Reassess when purpose, data combinations, threat conditions, or legal requirements change.

## Minimum classification record

For every dataset or data flow, document:

- Dataset/category name and purpose of processing (do not include actual identifiers).
- Factors `S`, `H`, `L`, and `V`, with a short reason for each score.
- IPCR total, assigned P1–P5 level, and any override.
- Owner, system/location, authorized roles, and retention expectation.
- Required protective controls and review date.
- A separate exposure-risk assessment reference, if one exists.

Never put real NIK, KK numbers, account numbers, credentials, or identity-document images into the public classification record.
