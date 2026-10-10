# Indonesian PII & Identifier Catalog

This folder catalogs personal-data categories and identifiers commonly encountered in Indonesian organizational environments. It supports the Indonesia OSINT & PII Protection Framework by helping an organization inventory data, estimate exposure impact, and select proportionate safeguards.

> **Important:** This catalog is a defensive reference, not a directory of people or a tool for discovering private records. Do not place real NIK, KK numbers, NPWP, phone numbers, account numbers, identity-document images, credentials, or other real personal data in this repository. Use synthetic examples only.

## How to use the catalog

1. Identify which categories your organization actually collects or processes.
2. Record the purpose, system/location, business owner, authorized roles, retention period, and lawful basis in an internal inventory. Keep that inventory private when it contains sensitive operational details.
3. Use the suggested baseline ranking in each category as a starting point, then assess the actual context with `framework/scoring-methodology.md`.
4. Apply the escalation rules in `framework/risk-escalation-rules.md` when identifiers are combined, data is exposed at scale, a child or vulnerable person is affected, or credentials are involved.
5. Select safeguards from `framework/protection-principles.md` and review the applicable legal requirements with qualified counsel or your privacy/legal team.

## Suggested baseline ranking

The P1–P5 labels below are the project's proposed internal criticality scale, not official government classifications and not direct legal categories under Indonesia's Personal Data Protection Law (UU PDP).

| Rank | Meaning | Typical response posture |
|---|---|---|
| P1 | Critical | Restrict access sharply; prevent public exposure; immediate incident triage if disclosed |
| P2 | Very High | Strong access control, encryption, masking, careful export and retention controls |
| P3 | High | Need-to-know access, secure sharing, monitoring, and retention limits |
| P4 | Moderate | Standard controlled access; reassess when linked with other fields |
| P5 | Low | Still assess identifiability, context, and combinations before publishing |

A baseline ranking is a prompt for assessment—not a promise that every instance of a field has the same risk. An identifier's rank can change depending on authenticity, completeness, scale, availability of other data, and possible harm.

## Categories

- [`civil-identity.md`](civil-identity.md) — NIK/KTP, KK, civil-registration records, signatures, and identity-document images.
- [`financial-and-tax.md`](financial-and-tax.md) — NIK/NPWP context, bank and payment details, income, tax records, and transactions.
- [`vehicle-and-transport.md`](vehicle-and-transport.md) — plate numbers, STNK, BPKB, SIM, and travel/transport records.
- [`health-and-employment.md`](health-and-employment.md) — health, BPJS, benefits, employee, payroll, and personnel records.
- [`education-and-government-ids.md`](education-and-government-ids.md) — NISN, NIM, child identity, passports, and other government or education identifiers.
- [`contact-and-digital-identity.md`](contact-and-digital-identity.md) — phone numbers, email, online accounts, device/network identifiers, and authentication secrets.
- [`other-indonesian-identifiers.md`](other-indonesian-identifiers.md) — property, utilities, business registrations, and other context-specific identifiers.

## Legal and reference notes

- Indonesia's [Law No. 27 of 2022 on Personal Data Protection (UU PDP)](https://peraturan.bpk.go.id/Details/229798/uu-no-27-) distinguishes specific and general personal data. The law identifies health data, biometric data, genetic data, criminal records, children's data, personal financial data, and other data under applicable legislation among specific personal data categories. Consult the legal text and qualified counsel for the full requirements.
- The [Directorate General of Taxes (DJP)](https://www.pajak.go.id/id/artikel/mudahkan-urusan-pajak-segerakan-validitas-data-nik-menjadi-npwp) describes the use of NIK as NPWP for resident individual taxpayers. Do not assume that every taxpayer, legal entity, or tax scenario uses the same identifier format; verify current rules with DJP.
- This project does not provide legal advice, determine lawful basis for processing, or replace a formal privacy impact assessment.

## Safe publication rules

- Never commit real personal-data samples or leaked databases.
- Do not use actual identity numbers in screenshots, example CSVs, issue reports, or test fixtures.
- Prefer synthetic values that are clearly marked as fictional and cannot reasonably be mistaken for valid identifiers.
- Redact screenshots and logs; remember that names, dates, locations, and combinations of fields can identify people even after a main ID number is hidden.
- If you encounter exposed personal data, do not download or redistribute it. Preserve only the minimum evidence necessary and report it through an appropriate, authorized channel.
