# Data Criticality vs Exposure Risk

## The key distinction

**Data criticality describes the importance of protecting the data. Exposure risk describes the seriousness of a current or credibly suspected path by which the data could be exposed or misused.** They are related but not interchangeable.

| Question | Data criticality (IPCR) | Exposure risk (ERS) |
|---|---|---|
| Main question | How serious could harm be if this data were mishandled? | How serious is the current or suspected exposure path? |
| Looks at | Sensitivity, potential harm, linkability, and subject/context vulnerability | Evidence/status, plausibly affected scope, accessibility, control weakness, and misuse/persistence indicators |
| Includes current control strength? | No | Yes |
| Includes current exposure evidence? | No | Yes |
| Includes number of records plausibly exposed? | No | Yes |
| Result labels | P1–P5 | ER1–ER5 |
| Main use | Select baseline protection and handling requirements | Set incident urgency and remediation priority |

IPCR is a proposed classification model for this project. ERS is a proposed exposure-risk model. Neither is an official Indonesian government classification or a substitute for legal or regulatory assessment.

## Example 1 — highly critical data, no current exposure indicator

A fictional company processes employee tax and payroll data. An authorized review found no exposure indicator, access is limited to relevant personnel, and the controls reviewed appear effective.

- **IPCR:** P2 — Very High, because the data could cause material identity, privacy, or financial harm if mishandled.
- **ERS:** ER5 — Low current exposure risk within the review's defined scope.
- **Decision:** Keep the strong P2-level safeguards. ER5 does not mean the information is public or safe to disclose.

## Example 2 — confirmed exposure with a broad impact

A fictional organization confirms that a public storage location exposed identity records and many records may be reachable. The source was readily accessible and containment is incomplete.

- **IPCR:** P1 or P2 depending on the actual fields, combinations, and likely harm.
- **ERS:** ER1 — Critical.
- **Decision:** Start incident response and containment immediately. Do not wait for evidence of fraud before taking reasonable protective action.

## Example 3 — lower-criticality field, high exposure risk

A fictional service exposes a large list of business contact details that are intended to be less sensitive individually, but the list is publicly accessible and has already been used for targeted phishing.

- **IPCR:** Could be P3 or P4 depending on the data and context.
- **ERS:** Could be ER1 or ER2 due to confirmed broad exposure and misuse.
- **Decision:** Prioritize containment and abuse response. Low-to-moderate data criticality does not cancel a serious exposure.

All examples are synthetic and should not be interpreted as automatic classifications for real datasets.

## Do not merge the scores

Do not add, average, multiply, or convert IPCR and ERS into a single number. Doing so hides important differences: one describes the data's potential impact; the other describes the current exposure conditions. Use them together with incident status, evidence confidence, and required legal/contractual obligations.

## Workflow

1. Define the authorized scope and data-processing purpose.
2. Identify the data category and assign IPCR using [`../framework/ipcr-ranking.md`](../framework/ipcr-ranking.md).
3. Assess any identified or suspected exposure pathway using [`../framework/exposure-risk-model.md`](../framework/exposure-risk-model.md).
4. Record incident status and evidence confidence separately from both scores.
5. Apply [`../framework/risk-escalation-rules.md`](../framework/risk-escalation-rules.md) to determine urgency and protective actions.
6. Record rationale, owner, due date, and verification steps without publishing real identifiers or exposed records.

## Reminder

A score is an internal decision aid, not proof that a breach occurred, not a legal classification, and not a basis to ignore applicable notification or response obligations.
