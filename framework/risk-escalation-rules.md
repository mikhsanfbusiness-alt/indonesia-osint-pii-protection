# Risk Escalation Rules

## Purpose

Use these rules after assigning two separate values:

- **IPCR P1–P5:** data criticality (the potential harm if the data is mishandled).
- **Exposure Risk ER1–ER5:** current or credibly suspected exposure risk (the evidence, scope, accessibility, controls, and misuse indicators surrounding an exposure path).

Also record incident status separately: no indicator found, suspected, probable, confirmed, contained, or remediated. These statuses are not score levels.

## Priority guidance: use both dimensions

Do not average, add, or collapse IPCR and exposure risk into one number. Use both dimensions to choose a response.

| Exposure risk | If data is IPCR P1/P2 | If data is IPCR P3–P5 |
|---|---|---|
| **ER1 — Critical** | Immediate incident escalation and coordinated containment, regardless of whether misuse is already proven. | Immediate incident triage and containment as appropriate; large scale, public access, or active misuse can make lower-criticality data urgent too. |
| **ER2 — Very High** | Urgent triage and containment review; involve security, privacy, system owner, and management as appropriate. | Urgent investigation and remediation, with priority based on evidence, scale, and possible harm. |
| **ER3 — High** | Prompt investigation with a named owner and near-term remediation plan; assess any need for incident escalation. | Prompt investigation and tracked remediation. |
| **ER4 — Moderate** | Maintain strong preventive controls for the highly critical dataset and promptly resolve observed gaps. | Planned remediation and periodic review. |
| **ER5 — Low** | Continue the controls required by IPCR; low current exposure risk does not mean low data sensitivity. | Maintain baseline controls and reassess when scope or context changes. |

This table is guidance, not a replacement for incident-response procedures or legal requirements. Any applicable mandatory action takes precedence.

## Minimum escalation triggers

Escalate immediately through the organization's incident-response process when:

- Valid credentials, active session tokens, API keys, private keys, or comparable secrets may have been exposed. Revoke or rotate them through approved procedures; invalidate sessions where appropriate.
- Unauthorized access to a sensitive system or dataset is confirmed or strongly indicated.
- A large data set may have been exfiltrated or left publicly accessible.
- Exposure involves children, health or biometric records, personal financial information, threats to physical safety, or other circumstances with potentially severe harm.
- The exposure remains active, containment is failing, or evidence indicates ongoing misuse.

For sensitive-data exposure, involve the security/incident lead and the appropriate data owner, privacy officer, legal counsel, and communications team. Determine applicable notification obligations through authorized legal/privacy review; scores cannot waive them.

## Unknown or incomplete evidence

- Do not describe an exposure as confirmed when the evidence is only an unverified allegation.
- Do not assume an unknown affected scope is small. Record the uncertainty and use a documented conservative provisional score when credible evidence suggests the issue may be wider.
- Do not download, test, mirror, or distribute suspected leaked records to verify an allegation.
- Prefer internal telemetry, approved configuration evidence, official advisories, trusted notifications, and reputable reporting.
- If authorization or scope is unclear, stop collection and escalate to the project or system owner.

## Decision record

For each escalation decision, record:

- Finding ID, assessment date, and accountable owner.
- IPCR level and factor rationale.
- ERS level, factor rationale, exposure status, and evidence limitations.
- Any override/minimum response floor and why it applies.
- Containment or mitigation action, responsible person/team, and deadline.
- Decision on further investigation, notification/legal review, and verification.
- Reassessment result and closure approval.

Do not place actual identifiers, credentials, leaked records, or sensitive evidence in a public GitHub report. Publish synthetic or irreversibly redacted examples only.
