# IPCR Scoring Methodology

## Overview

Use this scoring model to support consistent internal prioritization. It is a proposed portfolio framework, not an official standard. Organizations should validate the factors and thresholds against their own risk appetite and applicable obligations.

## Factors and weights

Rate each factor from **1 (low)** to **5 (very high)**, then calculate the weighted total.

| Factor | Weight | What to assess |
|---|---:|---|
| Sensitivity (`S`) | 6 | Potential privacy, safety, financial, or other harm if the data is exposed or misused |
| Misuse potential (`M`) | 5 | How readily the data could support fraud, impersonation, account compromise, discrimination, or other abuse |
| Exposure scale (`E`) | 4 | Number of people/records that could be affected, including whether the dataset is bulk or replicated |
| Linkability (`L`) | 3 | How easily the data can be combined with other information to identify or profile people |
| Control weakness (`C`) | 2 | Weakness in current safeguards, such as broad access, lack of encryption, exposed endpoints, or poor monitoring |

**Formula**

`IPCR Score = (S × 6) + (M × 5) + (E × 4) + (L × 3) + (C × 2)`

Minimum score: **20**. Maximum score: **100**.

## Rating guide

| Rating | 1 — Low | 2 — Limited | 3 — Moderate | 4 — High | 5 — Very high |
|---|---|---|---|---|---|
| Sensitivity | Little personal impact | Limited contact/context data | Identifiable personal or work data | Strong identity, financial, or private-life impact | Authentication secrets, highly sensitive records, or potentially severe harm |
| Misuse potential | Little practical abuse | Requires substantial additional information | Could support targeted scams | Enables credible fraud or identity abuse | Direct compromise, high-impact fraud, or severe abuse is plausible |
| Exposure scale | One or very few records | Small, contained set | Multiple users or department | Large business unit/customer segment | Bulk, widespread, or unknown potentially large exposure |
| Linkability | Not identifying in context | Difficult to link | Linkable with common information | Easily linked to identity or other records | Enables a detailed identity profile or re-identification |
| Control weakness | Strong, reviewed controls | Minor gaps | Some missing controls | Weak access/monitoring or unnecessary copies | Publicly accessible, uncontrolled, or already confirmed exposed |

Use the rating descriptions as prompts, not mechanical truth. Write a short evidence-based reason for every factor score. If record count or exposure is unknown, record that uncertainty rather than inventing a number.

## Score bands

| Total score | IPCR level |
|---:|---|
| 80–100 | P1 — Critical |
| 65–79 | P2 — Very High |
| 45–64 | P3 — High |
| 25–44 | P4 — Moderate |
| 20–24 | P5 — Low |

## Worked example (synthetic)

Scenario: a fictional company stores employee contact details with work records. The dataset does not include identity-document images, authentication secrets, or health information. Some fields can be linked to publicly available professional information.

- Sensitivity: `S = 3`
- Misuse potential: `M = 3`
- Exposure scale: `E = 3`
- Linkability: `L = 3`
- Control weakness: `C = 2`

Calculation: `(3×6) + (3×5) + (3×4) + (3×3) + (2×2) = 56` → **P3 — High**.

This example is illustrative. A real assessment could score differently based on the actual fields, number of records, context, and controls.

## Criticality floor and overrides

The weighted score must not reduce a clearly severe case. At minimum, review for these overrides:

- Valid credentials, active tokens, private keys, or secrets exposed: treat as **P1 until invalidated and investigated**.
- Confirmed large-scale exposure of highly sensitive data: consider **P1**, with immediate incident assessment.
- Full identity-document packages or combinations that materially enable identity fraud: normally no lower than **P2**, unless a documented review justifies otherwise.
- Data involving children, vulnerable people, safety risks, or sensitive context: escalate for specialist review; do not rely on score alone.
- Confirmed exposure or evidence of active exploitation: assign incident severity separately and trigger the incident response process.

Document any override, its rationale, approver, and date.

## Good scoring practice

- Score a clearly defined dataset or data flow, not an entire company vaguely.
- Use actual controls and available evidence, not assumptions.
- Distinguish inherent criticality from residual risk after controls.
- Ask a data owner or privacy/security reviewer to validate material decisions.
- Reassess after major changes, incidents, or at least on the organization's review cycle.
