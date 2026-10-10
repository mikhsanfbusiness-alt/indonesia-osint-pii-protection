# Scoring Methodology: Data Criticality vs Exposure Risk

## Purpose

Use two independent scores to avoid confusing the importance of protecting data with the urgency of a current security exposure.

- **IPCR (P1–P5): data criticality.** How harmful could it be if this category or dataset were mishandled, disclosed, or misused, given its content and context? It does not score current controls, current exposure status, or the number of records affected by an incident.
- **Exposure Risk (ER1–ER5): current exposure risk.** How serious is a known or credibly suspected exposure pathway, given evidence, plausible exposed scope, accessibility, control gaps, and indicators of misuse?

These are proposed portfolio methods, not official government classifications. Organizations should validate thresholds and decisions against their own risk methodology and applicable obligations.

## Model A — IPCR data criticality

Rate each factor 1 (low) to 5 (very high):

| Factor | Weight | Assessment question |
|---|---:|---|
| Sensitivity (`S`) | 6 | How sensitive is this type of information in this context? |
| Potential harm (`H`) | 6 | How severe could the harm be if it were mishandled or misused? |
| Linkability (`L`) | 4 | How readily could it identify, single out, or profile a person when combined with relevant information? |
| Vulnerability/context (`V`) | 4 | Does the subject population or context amplify potential harm? |

`IPCR = (S × 6) + (H × 6) + (L × 4) + (V × 4)`

Score range: 20–100. Bands: 80–100 P1 Critical; 65–79 P2 Very High; 45–64 P3 High; 25–44 P4 Moderate; 20–24 P5 Low.

Full definitions and Indonesian examples: [IPCR Ranking](ipcr-ranking.md).

## Model B — Exposure Risk Score (ERS)

Rate each factor 1 (low) to 5 (very high), based on evidence about the identified or suspected exposure pathway:

| Factor | Weight | Assessment question |
|---|---:|---|
| Exposure evidence/status (`E`) | 6 | How strong is the evidence that unauthorized exposure or access exists? |
| Affected/reachable scope (`N`) | 5 | How many records or people are plausibly affected or reachable through this issue? |
| Accessibility/exploitability (`A`) | 4 | How easily could an unauthorized party access or use the data through the identified path? |
| Control/containment weakness (`C`) | 3 | How weak are relevant access, detection, and containment controls? |
| Misuse/persistence indicators (`M`) | 2 | Is there credible evidence of attempted or ongoing misuse or continued access? |

`ERS = (E × 6) + (N × 5) + (A × 4) + (C × 3) + (M × 2)`

Score range: 20–100. Bands: 80–100 ER1 Critical; 65–79 ER2 Very High; 45–64 ER3 High; 25–44 ER4 Moderate; 20–24 ER5 Low.

Factor scales, evidence limits, examples, and overrides: [Exposure Risk Model](exposure-risk-model.md).

## Why the two scores must stay separate

- A dataset of tax and payroll records may be **IPCR P2** even when no exposure is known and safeguards have been validated, resulting in a low current exposure-risk score. The data still requires strong baseline controls.
- A lower-criticality dataset may have **ER1** if a confirmed public exposure affects many people or is being actively abused.
- Strong controls should affect exposure risk, not reduce the inherent criticality assigned to the data.
- A large record count should affect plausible exposure scope, not automatically raise the intrinsic criticality of every record.

**Do not add, average, multiply, or collapse IPCR and ERS into one score.** Use the two-dimensional decision guidance in [`risk-escalation-rules.md`](risk-escalation-rules.md) and assess incident status separately.

## Evidence and quality safeguards

- Score a defined dataset, data flow, or exposure path—not a whole company vaguely.
- Provide a brief evidence-based reason for every factor score.
- Never access, download, or test real leaked records solely to improve a score. Use approved internal evidence, official notices, or reputable incident reporting.
- If scale is unknown, record it as unknown. Use a conservative provisional value only where evidence supports a plausible wider exposure, and explain the assumption.
- A score is not a legal determination, proof of a breach, or a decision that statutory notification can be ignored.
- Document the reviewer, date, assumptions, overrides, owner, and reassessment trigger.
