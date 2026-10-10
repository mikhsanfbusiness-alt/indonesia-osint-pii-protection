# IPCR Risk Escalation Rules

## Purpose

These rules help teams decide when a data classification or suspected exposure needs extra review. They are proposed internal guidance, not official Indonesian government severity levels. Follow the organization's incident response plan and applicable reporting obligations.

## Escalation triggers

### Immediate security response

Start the organization's incident response process immediately when any of the following is suspected:

- Active passwords, session tokens, private keys, API keys, or privileged secrets are exposed.
- A database or storage location containing personal data is publicly accessible without authorization.
- There is evidence of data exfiltration, bulk download, extortion, or active misuse.
- A large dataset of identity, financial, health, biometric, or child-related information may have been exposed.
- Exposure may create an imminent safety risk to an individual or group.

Do not wait for a perfect IPCR score before escalating a credible high-impact incident.

### Raise the minimum classification

Apply the following suggested minimums, unless a documented review determines the trigger does not apply:

| Condition | Suggested minimum level | Why |
|---|---|---|
| Valid authentication secret or privileged token exposed | P1 | May provide direct system/account access |
| Confirmed widespread exposure of highly sensitive personal data | P1 | Potential for severe, broad impact |
| Complete identity-document package or closely linked identity set | P2 | Increased potential for impersonation or identity fraud |
| Personal data combined with home address, financial details, or authentication information | P2 or higher | Combined information can materially increase harm |
| Data concerning children, vulnerable people, or safety-sensitive situations | Specialist review; usually raise priority | Potential harm may be disproportionate to record count |
| Exposure scope is unknown and evidence supports possible bulk access | Temporary conservative level; investigate promptly | Unknown scale is not evidence of low risk |

These floors are recommendations for the project. Organizations should tailor them to context and document changes.

## Incident severity is separate from data criticality

IPCR describes how critical the data is to protect. Incident severity should separately consider:

- Whether access or disclosure actually occurred, rather than merely being theoretically possible
- How long the exposure lasted
- Number and type of people or records affected
- Whether data was copied, indexed, downloaded, or misused
- Whether access has been contained and credentials invalidated
- Legal, contractual, customer, operational, financial, and safety impacts

A P1 dataset does not automatically prove a P1 incident. Similarly, a dataset with a lower baseline rating may still be involved in a severe incident if the exposure is widespread or actively exploited.

## Initial response checklist

- [ ] Notify the designated security/privacy incident owner using approved internal channels.
- [ ] Preserve relevant logs and evidence in accordance with policy; avoid unnecessary copying of exposed personal data.
- [ ] Restrict access or isolate the affected system where appropriate and authorized.
- [ ] Invalidate exposed credentials or tokens and assess related systems.
- [ ] Establish the likely time window, data categories, and potential scope.
- [ ] Record verified facts separately from hypotheses.
- [ ] Involve legal, privacy, communications, and business owners as appropriate.
- [ ] Assess applicable notification, contractual, and regulatory obligations with the responsible team.
- [ ] Document containment, recovery, and follow-up preventive actions.

## Evidence and escalation record

Record only what is needed to coordinate the response:

- Case/reference ID
- Discovery date and time with timezone
- System or dataset identifier (not the actual personal data)
- Categories potentially affected
- Estimated scale and confidence level
- Actions taken, owner, and timestamps
- Rationale for classification and any override
- Next review time and closure criteria

Never publish exposed records, live credentials, unredacted documents, or personal identity values in a public repository.
