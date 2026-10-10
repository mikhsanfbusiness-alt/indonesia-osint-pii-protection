# Indonesian PII & Identifier Catalog

This folder catalogs personal-data categories and identifiers commonly encountered in Indonesian organizational environments. It supports the Indonesia OSINT & PII Protection Framework by helping organizations inventory data, assess its criticality, and select proportionate safeguards.

> **Important:** This catalog is a defensive reference, not a directory of people or a tool for discovering private records. Do not place real NIK, KK numbers, NPWP, phone numbers, account numbers, identity-document images, credentials, or other real personal data in this repository. Use synthetic examples only.

## How to use the catalog

1. Identify which categories your organization actually collects or processes.
2. Record the purpose, system/location, business owner, authorized roles, retention period, and lawful basis in an internal inventory. Keep that inventory private when it contains sensitive operational details.
3. Use the suggested baseline P1–P5 ranking as an initial **data criticality** estimate. It is not an exposure-risk assessment.
4. Use [`../framework/scoring-methodology.md`](../framework/scoring-methodology.md) and [`../framework/ipcr-ranking.md`](../framework/ipcr-ranking.md) to assess criticality. If an exposure path is known or credibly suspected, assess it separately with [`../framework/exposure-risk-model.md`](../framework/exposure-risk-model.md).
5. Apply [`../framework/risk-escalation-rules.md`](../framework/risk-escalation-rules.md) when sensitive data is exposed, records may be reachable at scale, a child or vulnerable person is affected, or credentials are involved.
6. Select safeguards from [`../framework/protection-principles.md`](../framework/protection-principles.md) and review applicable legal requirements with qualified counsel or your privacy/legal team.

## Suggested baseline data-criticality ranking

The P1–P5 labels below are the project's proposed internal criticality scale, not official government classifications and not direct legal categories under Indonesia's Personal Data Protection Law (UU PDP).

| Rank | Meaning | Typical protection posture |
|---|---|---|
| P1 | Critical | Strictly restrict access; strong encryption and logging; minimize copies and retention; prepare incident procedures. |
| P2 | Very High | Strong access control, encryption, masking, careful export and retention controls. |
| P3 | High | Need-to-know access, secure sharing, monitoring, and retention limits. |
| P4 | Moderate | Standard controlled access; reassess when linked with other fields. |
| P5 | Low | Maintain baseline safeguards and confirm context and combinations before publishing. |

A baseline ranking is a prompt for assessment—not a promise that every instance of a field has the same criticality. Criticality depends on sensitivity, plausible harm, linkability, and context. Current control weakness, incident status, and the number of records actually exposed belong in a separate exposure-risk assessment.

## Categories

- [`civil-identity.md`](civil-identity.md) — NIK/KTP, KK, civil-registration records, signatures, and identity-document images.
- [`financial-and-tax.md`](financial-and-tax.md) — NIK/NPWP context, bank and payment details, income, tax records, and transactions.
- [`vehicle-and-transport.md`](vehicle-and-transport.md) — plate numbers, STNK, BPKB, SIM, and travel/transport records.
- [`health-and-employment.md`](health-and-employment.md) — health, BPJS, benefits, employee, payroll, and personnel records.
- [`education-and-government-ids.md`](education-and-government-ids.md) — NISN, NIM, child identity, passports, and other government or education identifiers.
- [`contact-and-digital-identity.md`](contact-and-digital-identity.md) — phone numbers, email, online accounts, device/network identifiers, and authentication secrets.
- [`other-indonesian-identifiers.md`](other-indonesian-identifiers.md) — property, utilities, business registrations, and other context-specific identifiers.

## Legal and reference notes

- Indonesia's [Law No. 27 of 2022 on Personal Data Protection (UU PDP)](https://peraturan.bpk.go.id/Details/229798/uu-no-27-) distinguishes specific and general personal data. Consult the legal text and qualified counsel for full requirements and context.
- The [Directorate General of Taxes (DJP)](https://www.pajak.go.id/id/artikel/mudahkan-urusan-pajak-segerakan-validitas-data-nik-menjadi-npwp) describes the use of NIK as NPWP for resident individual taxpayers. Do not assume every taxpayer, legal entity, or tax scenario uses the same identifier format; verify current rules with DJP.
- This project does not provide legal advice, determine a lawful basis for processing, or replace a formal privacy impact assessment.

## Safe publication rules

- Never commit real personal-data samples or leaked databases.
- Do not use actual identity numbers in screenshots, example CSVs, issue reports, or test fixtures.
- Prefer synthetic values clearly marked as fictional and not reasonably mistaken for valid identifiers.
- Redact screenshots and logs; names, dates, locations, and combinations of fields can identify people even after a main ID number is hidden.
- If you encounter exposed personal data, do not download or redistribute it. Preserve only the minimum evidence necessary and report it through an appropriate, authorized channel.
