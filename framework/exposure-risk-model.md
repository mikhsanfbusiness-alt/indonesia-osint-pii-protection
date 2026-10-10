# Exposure Risk Model

## Purpose

This model assesses the **current or credibly suspected risk of exposure** for a defined dataset, system, or data flow. It complements the [Indonesia PII Criticality Ranking (IPCR)](ipcr-ranking.md), which assesses the criticality of the data itself.

Exposure risk asks:

> **Given the available evidence and current conditions, how serious is the identified or suspected exposure pathway?**

A high data-criticality rating does not prove that exposure has occurred. A low exposure-risk score does not mean a sensitive dataset can be handled casually.

## Factors and weights

Rate each factor from 1 (low) to 5 (very high). Scores must be supported by approved evidence and the scope of the assessment.

| Factor | Weight | Guidance for assigning a score |
|---|---:|---|
| Exposure evidence/status (`E`) | 6 | **1:** scoped review found no indicator and relevant controls were checked; **2:** no confirmed exposure, but visibility is limited; **3:** credible but unverified report or suspected weakness; **4:** unauthorized access is strongly indicated or a limited exposure is confirmed; **5:** confirmed unauthorized access, uncontrolled public accessibility, or exfiltration. |
| Affected/reachable scope (`N`) | 5 | **1:** no or very few records plausibly reachable; **2:** a small, bounded set; **3:** multiple users or a team; **4:** a large customer/employee segment; **5:** mass exposure or a credible indication the scope is wider than the verified sample. Do not assume a large scope merely because it is unknown. |
| Accessibility/exploitability (`A`) | 4 | **1:** no demonstrated path and strong barriers; **2:** substantial barriers, with some uncertainty; **3:** limited access path or meaningful barriers remain; **4:** unauthorized access could require relatively little effort; **5:** direct public accessibility or an exposed active secret makes access readily possible. Never probe or retrieve real records to assign this score. |
| Control/containment weakness (`C`) | 3 | **1:** effective access controls and containment are verified; **2:** minor gaps; **3:** material gaps in controls or monitoring; **4:** weak restrictions or delayed containment; **5:** controls are absent, bypassed, or the exposure remains uncontrolled. |
| Misuse/persistence indicators (`M`) | 2 | **1:** no known indicators; **2:** isolated, unverified signals; **3:** credible attempts or suspicious patterns; **4:** confirmed limited misuse or repeated unauthorized attempts; **5:** ongoing abuse, continued unauthorized access, or broad exploitation is confirmed. |

**Formula:**

`ERS = (E × 6) + (N × 5) + (A × 4) + (C × 3) + (M × 2)`

Minimum score: **20**. Maximum score: **100**.

## Exposure-risk bands

| Score | Level | Default action posture |
|---:|---|---|
| 80–100 | **ER1 — Critical** | Immediate incident escalation and coordinated containment/response. |
| 65–79 | **ER2 — Very High** | Urgent triage, access restriction, and management/security/privacy review. |
| 45–64 | **ER3 — High** | Prompt investigation and remediation with an accountable owner and deadline. |
| 25–44 | **ER4 — Moderate** | Address observed gaps on a planned, tracked timeline; reassess after changes. |
| 20–24 | **ER5 — Low** | No material exposure indicator was identified in the defined scope; maintain controls and review when conditions change. |

The bands are project-defined and must not be treated as official Indonesian incident-severity levels.

## Evidence status is not the same as score

In every assessment, also record a plain-language status separately:

- **No indicator found in scoped review** — not proof that no exposure exists.
- **Suspected** — a possible issue or report needs validation through authorized, safe methods.
- **Probable** — multiple credible indicators support exposure, but confirmation is incomplete.
- **Confirmed** — reliable evidence establishes unauthorized exposure or access.
- **Contained / under investigation / remediated** — operational state after response; retain the incident history.

Do not change “suspected” to “confirmed” solely because a numerical threshold is crossed. Similarly, a low score must not override credible evidence of a breach or applicable reporting obligations.

## Worked examples (synthetic)

### Example A — sensitive dataset, no known exposure

A fictional company stores employee tax and payroll records. A scoped review found no exposure indicators, relevant access controls were checked, and no misuse indicators were found. The data could still be highly critical under IPCR.

- `E=1`, `N=1`, `A=1`, `C=1`, `M=1`
- `ERS = (1×6)+(1×5)+(1×4)+(1×3)+(1×2) = 20`
- Result: **ER5 — Low current exposure risk**, subject to the scope and limits of the review.
- Separate data classification: the dataset may still be **IPCR P2 — Very High** and must retain the controls required for that criticality.

### Example B — confirmed uncontrolled exposure

A fictional incident report and authorized internal confirmation establish that a public storage location exposed a large set of identity records. The location was readily accessible and containment has not been verified. There is no confirmed evidence of misuse yet.

- `E=5`, `N=4`, `A=5`, `C=5`, `M=2`
- `ERS = (5×6)+(4×5)+(5×4)+(5×3)+(2×2) = 89`
- Result: **ER1 — Critical**. Start incident response immediately; do not wait for proof of misuse.

These examples are synthetic and illustrative. Real scores require evidence, context, and review.

## Overrides and minimum response floors

Apply the stronger response when a clear severe condition exists, regardless of the arithmetic score:

- Valid exposed passwords, active session tokens, API keys, or private keys that enable access: treat as **ER1 until revoked/invalidated and investigated**.
- Confirmed large-scale exfiltration or ongoing unauthorized access to sensitive personal data: treat as **ER1** pending incident-lead review.
- Confirmed unauthorized exposure of P1/P2 data: at least **ER2** and immediate triage; elevate to ER1 where the exposure is broad, uncontrolled, or likely to cause severe harm.
- Credible evidence involving children, vulnerable people, physical safety, or ongoing exploitation requires specialist review and may justify a higher response priority.
- An unverified online claim alone is not proof. Record the claim, source quality, and uncertainty; use safe authorized confirmation methods.

Record the override, evidence, decision-maker, timestamp, and follow-up actions. These response floors are proposed internal safeguards, not legal definitions.

## Safe assessment process

1. Confirm the authorized scope and permitted evidence sources.
2. Prefer internal logs, approved configuration evidence, trusted notifications, official advisories, and reputable incident reports.
3. Record only the data categories and minimum evidence needed; do not copy raw NIK, KK, NPWP, financial values, credentials, or leaked records into public materials.
4. Do not download, redistribute, or probe a suspected leaked database to estimate scale.
5. Contain and report confirmed exposures through the organization's incident-response process. Engage security, privacy, legal, and system owners as appropriate.
6. Re-score after containment or remediation and retain the original assessment for audit history.

## References and limitations

This is a project-defined risk-prioritization model, not a certified methodology, official incident severity taxonomy, legal opinion, or substitute for an organization's incident-response and regulatory-notification requirements. Consult applicable laws, contracts, sector requirements, and qualified professionals.
