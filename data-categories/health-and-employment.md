# Health, Social Protection & Employment Data

## Purpose

This category covers health and insurance records, employee files, payroll, and work-related identifiers. Some information in this category may fall within specific personal data under Indonesia's Personal Data Protection Law (UU PDP), depending on the data type and context.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| Medical and health records | Diagnoses, prescriptions, lab results, treatment, disability-related information | P2; consider P1 for mass exposure or highly sensitive records | Discrimination, extortion, stigma, privacy harm | Strict role-based access; encryption; detailed audit logs; minimal retention |
| Health insurance | BPJS Kesehatan membership details, participant numbers, service/claim information | P2–P3; raise when linked to medical records or identity documents | Impersonation, service abuse, health-related privacy exposure | Mask numbers; restrict claim data; secure provider exchanges |
| Employment insurance | BPJS Ketenagakerjaan/KPJ-related records, claims, benefits | P2–P3 | Benefits fraud, employment and financial privacy exposure | Limit access to authorized HR/benefits staff; protect exports |
| Employee identity | Employee number, NIP where applicable, personnel profile, work contact | P3; reassess with additional identifiers | Targeted phishing, internal impersonation, profiling | Least privilege; directory-data minimization; secure identity verification |
| Payroll and compensation | Salary, bonus, bank destination, tax deductions, payroll files | P2 | Financial fraud, extortion, workplace harm | Segregate payroll duties; encryption; access logs; approval workflows |
| Personnel files | Contracts, disciplinary records, performance reviews, emergency contacts | P2–P3 depending on contents | Unfair treatment, exposure of confidential employment matters | Separate sensitive HR records; restricted sharing; defined retention |
| Biometrics used at work | Fingerprints, facial templates, voiceprints, access-control templates | P2; consider P1 at scale | Irreplaceable identifier exposure and unauthorized tracking | Avoid collection when unnecessary; protect templates; restrict and audit access |

## Assessment checklist

- [ ] Separate health records from general HR files and routine employee directories.
- [ ] Limit health information to roles that need it for a defined purpose.
- [ ] Mask membership and employee numbers in reports and support interfaces.
- [ ] Restrict payroll exports and require secure transfer and approval.
- [ ] Minimize collection of emergency contacts and family details.
- [ ] Set separate retention periods for medical, payroll, and personnel records.
- [ ] Use fictional people and synthetic records in demos.

## Escalation considerations

The UU PDP identifies health data, biometric data, children's data, and personal financial data among specific personal data categories. If a suspected exposure concerns these categories, prioritize incident triage and legal/privacy review. The suggested P-rank in this file is an internal starting point; final severity depends on scale, detail, context, and likely harm.

Reference: [UU No. 27 Tahun 2022 — Pelindungan Data Pribadi](https://peraturan.bpk.go.id/Details/229798/uu-no-27-).
