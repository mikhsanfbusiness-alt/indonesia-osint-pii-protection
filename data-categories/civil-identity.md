# Civil Identity & Family Records

## Purpose

This category covers records used to establish or describe a person's civil identity, household, family relationships, or legal status in Indonesia.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| National identity | NIK; KTP/e-KTP data; name; place/date of birth | P2 | Identity impersonation, targeted fraud, cross-database linking | Encrypt at rest/in transit; mask displays; tightly restrict search/export; log access |
| Family-card records | Nomor KK; household members; family relationships; registered address | P2 | Household profiling, impersonation, social engineering against relatives | Limit access by job role; minimize copies; prevent bulk downloads; redact in reports |
| Identity-document images | KTP scans/photos, document numbers, signatures, portrait | P2; consider P1 if bulk or combined with access/financial data | Document forgery, impersonation, fraud | Store in controlled document systems; watermark copies when appropriate; strict retention and sharing rules |
| Civil-status records | Birth/marriage/divorce/death certificate details and associated records | P2–P3 depending on completeness and context | Identity fraud, discrimination, family privacy harms | Restrict access; redact nonessential fields; document purpose and retention |
| Identity attributes | Full name, aliases, place/date of birth, sex/gender where recorded, nationality, marital status | P3 alone; reassess when combined | Re-identification, profiling, targeted phishing | Collect only required attributes; avoid publishing combinations unnecessarily |
| Signature and identity proof | Handwritten/electronic signature images, specimen signatures, document verification artifacts | P2; consider P1 if directly usable for transactions | Forgery, fraudulent authorization | Treat as restricted; do not include in public samples; monitor access and sharing |

## Assessment checklist

- [ ] Confirm why each field is needed and which team owns it.
- [ ] Identify every system, export, backup, shared folder, and vendor that stores the data.
- [ ] Determine whether the record can be combined with financial, contact, health, or authentication data.
- [ ] Mask identifiers in user interfaces and reports where full values are unnecessary.
- [ ] Restrict bulk search and export; alert on unusual access patterns.
- [ ] Set a justified retention period and a secure deletion process.
- [ ] Use synthetic examples in testing and public documentation.

## Escalation considerations

Raise the assigned criticality when a record includes multiple identity proofs, is linked to account recovery or financial services, affects children or vulnerable people, or involves many individuals. Treat suspected mass exposure as an incident even if some fields are incomplete. Do not try to validate exposed identity records by querying restricted systems.

## Notes

NIK is a unique population identifier and may also be used as NPWP for resident individual taxpayers under the applicable tax framework. That linkage increases the importance of preventing unnecessary copying and uncontrolled correlation. Verify current administrative requirements with official authorities.
