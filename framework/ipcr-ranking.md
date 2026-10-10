# Indonesia PII Criticality Ranking (IPCR)

## Purpose

The Indonesia PII Criticality Ranking (IPCR) is a proposed internal framework for helping an organization prioritize protection for personal data it processes. It is designed for defensive security, privacy risk assessment, and awareness activities in the Indonesian context.

**IPCR is not an official Indonesian government classification and is not legal advice.** Use it alongside applicable laws, contracts, sector-specific requirements, and the organization's approved risk methodology.

## Ranking levels

| Level | Score | Meaning | Typical handling expectation |
|---|---:|---|---|
| **P1 — Critical** | 80–100 | Exposure could enable immediate compromise, severe harm, or widespread abuse. | Strictly restricted access; strong encryption; detailed audit logging; minimize copies and retention; incident escalation immediately. |
| **P2 — Very High** | 65–79 | Data could materially enable identity fraud, serious privacy harm, or targeted abuse. | Need-to-know access; encryption; masking in routine views; controlled exports; periodic access review. |
| **P3 — High** | 45–64 | Data could facilitate targeted scams, profiling, or harm when exposed or linked with other information. | Role-based access; secure transfer and storage; retention limits; monitored exports. |
| **P4 — Moderate** | 25–44 | Standalone exposure may be less harmful, but context or linkage can increase risk. | Standard access controls; avoid unnecessary publication; monitor combinations and bulk exports. |
| **P5 — Low** | 20–24 | Information has limited impact in the assessed context, often because it is intentionally public or has little identifying value alone. | Maintain basic safeguards and reassess if context changes. |

The score range begins at 20 because the five scoring factors each receive a minimum score of 1.

## Indonesian data examples (starting point only)

The examples below are **not automatic legal or universal classifications**. Assign a score for the actual dataset, processing purpose, number of affected people, and surrounding controls.

| Data category | Starting consideration | Factors that may increase criticality |
|---|---|---|
| Passwords, active session tokens, API keys, private keys | Often P1 if valid or exposed | Privileged access, production systems, reusable credentials, broad access |
| NIK/KTP, KK number, identity document images | Often P2 or higher depending on context | Combined with full name, address, signature, date of birth, or other identifiers; bulk exposure |
| Health records, biometric or genetic data | Often P2 or P1 for highly sensitive or bulk exposure | Scale, potential discrimination, medical detail, ease of re-identification |
| Bank details, financial records, payment data | Context-dependent; P2 or higher where actionable | Credentials, transaction details, balances, authentication factors, bulk exposure |
| NPWP and tax documents | Often P2–P3 depending on completeness and context | Identity documents, financial details, signatures, company authorization data |
| BPJS/KPJ, employment and payroll records | Often P2–P3 depending on fields | Health, salary, bank details, government identifiers, bulk records |
| Phone number, personal email, home address | Often P3–P4 alone | Combined with identifiers, security questions, stalking risk, large-scale exposure |
| Vehicle plate number (nopol) | Context-dependent, often P4 alone | Linked to owner identity, home/work location, STNK/BPKB images, location patterns |
| NIM/NISN, NIP, internal employee ID | Context-dependent, often P3–P4 | Children or vulnerable groups, linked records, authentication use, bulk exposure |
| Public business contact address or role mailbox | May be P5 in the intended public context | Misconfiguration, internal routing details, or combination with nonpublic records |

## Classification principles

1. **Classify the data in context, not by field name alone.** A vehicle plate alone is not equivalent to a plate plus owner address and document images.
2. **Consider combinations.** Multiple low- or medium-risk fields can collectively create a high-risk identity profile.
3. **Separate data criticality from incident severity.** Criticality describes the potential sensitivity and impact if mishandled; incident severity also depends on whether exposure occurred, exploitability, scale, and containment.
4. **Use a minimum criticality floor.** Escalation rules can raise a score-based level when a clear high-risk condition exists.
5. **Record uncertainty.** When evidence is incomplete, state assumptions and use a conservative temporary classification until reviewed.
6. **Review periodically.** Reassess when processing purposes, systems, data combinations, threat conditions, or legal requirements change.

## Minimum record for each classification

For every data asset or dataset, document:

- Data category and purpose of processing
- Whether the dataset contains direct identifiers, sensitive details, or authentication secrets
- Approximate number of affected people or records (where known)
- Linkability with other datasets
- Storage location and authorized roles
- IPCR factor scores and rationale
- Assigned level, required controls, owner, and review date

Do not put real NIK, KK numbers, account numbers, credentials, or other direct identifiers into the classification record. Use synthetic examples or non-identifying references.
