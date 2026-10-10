# Education & Other Government-Issued Identifiers

## Purpose

This category covers student, child, travel, immigration, and other government-related identifiers that may be processed by schools, universities, employers, public bodies, and service providers.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| Student identity | NISN, NIM, student number, academic account ID | P3–P4 alone; raise when linked to identity or academic records | Student profiling, impersonation, targeted scams | Limit public display; control directory access; mask in examples |
| Child identity | Kartu Identitas Anak (KIA), child's identity and guardian details | P2; consider P1 for mass records or combined identity documents | Risks to children, identity fraud, exposure of family relationships | Strong access controls; minimize collection; extra caution with public reports |
| Academic records | Grades, attendance, disciplinary records, accommodations, transcripts | P2–P3 depending on sensitivity | Stigma, discrimination, impersonation, privacy harm | Restrict to authorized staff/student; secure sharing; documented retention |
| Passport and travel documents | Passport number, visa/permit information, document scans | P2 | Identity/travel-document fraud, impersonation | Restricted document management; redact scans; minimize copies |
| Public-service identifiers | Reference numbers, service-account IDs, permits, certificates, application numbers | P3–P4 depending on linked data | Account targeting, re-identification, service fraud | Mask in public records; restrict access to linked profiles |
| Public-sector personnel identifiers | NIP and employee profile details, where applicable | P3; raise with identity or access details | Employee impersonation, targeted phishing | Restrict internal staff records; avoid exposing non-public employee fields |
| Government credentials or access tokens | Login secrets, active tokens, private keys used for government-related systems | P1 if active or usable | Unauthorized system access, privilege abuse, data compromise | Revoke/rotate promptly; preserve security evidence; follow incident-response procedures |

## Assessment checklist

- [ ] Identify whether the records relate to a child or another vulnerable person.
- [ ] Separate student directory fields from grades, discipline, health, or accommodation details.
- [ ] Avoid publishing document scans, student lists, or class-level datasets.
- [ ] Check whether a government/service reference reveals further information when combined with other sources.
- [ ] Restrict staff identifiers and internal access information to legitimate recipients.
- [ ] Remove real names, IDs, dates of birth, and school details from examples.

## Escalation considerations

Children's personal data is identified among the specific personal data categories in UU PDP. Do not treat an education identifier as harmless simply because it is a number. A student number linked to a child's name, school, schedule, address, or health/disciplinary records can raise the risk significantly.

Reference: [UU No. 27 Tahun 2022 — Pelindungan Data Pribadi](https://peraturan.bpk.go.id/Details/229798/uu-no-27-).
