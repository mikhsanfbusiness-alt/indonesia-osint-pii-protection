# Financial, Payment & Tax Data

## Purpose

This category covers personal financial information and tax-administration data processed by employers, financial institutions, merchants, service providers, and other organizations.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| Tax identity | NIK used as NPWP for eligible resident individual taxpayers; NPWP records; taxpayer profile | P2–P3 depending on scope | Identity linking, tax-themed social engineering, disclosure of financial affairs | Restrict access; mask IDs; audit exports; verify current tax rules with DJP |
| Bank account data | Account number, account-holder name, bank details, statements | P2; consider P1 in bulk or combined with credentials | Fraud, targeted impersonation, exposure of financial activity | Encrypt; restrict downloads; segregate duties; monitor unusual access |
| Payment card data | Cardholder details, payment tokens, card data handled by the business | P1–P2 depending on data and controls | Unauthorized transactions and financial fraud | Avoid storing sensitive authentication data; use approved payment providers; follow applicable industry standards |
| E-wallet and payment identifiers | Wallet ID/phone number, payment handles, transaction references | P3; raise if paired with account access or transaction histories | Account targeting, scam attempts, transaction profiling | Mask identifiers; apply transaction monitoring; restrict support-agent visibility |
| Income and employment finance | Salary, payroll, bonus, deductions, bank destination | P2–P3 | Privacy harm, extortion, fraud, workplace harm | Strong role-based access; encrypted transfer; controlled payroll exports |
| Tax and accounting documents | Tax returns, withholding records, invoices, personal tax documents | P2–P3 | Financial profiling, fraud, business or personal confidentiality loss | Secure document storage; least privilege; retention schedule; redacted test copies |
| Transaction history | Purchase history, transfer details, payment timestamps, locations, counterparties | P2–P3; raise for sensitive inference or mass data | Financial profiling, stalking, targeted social engineering | Limit purpose and retention; tokenize where possible; monitor bulk queries |

## Special note: NIK and NPWP

DJP has published guidance on using NIK as NPWP for resident individual taxpayers. Do not treat NIK and NPWP as always separate independent identifiers, or assume the same identifier format applies to every taxpayer category. Confirm the applicable case using current official DJP guidance.

Reference: [DJP — Validating NIK as NPWP](https://www.pajak.go.id/id/artikel/mudahkan-urusan-pajak-segerakan-validitas-data-nik-menjadi-npwp).

## Assessment checklist

- [ ] Separate identity data from transaction details where practical.
- [ ] Do not store passwords, PINs, CVVs, one-time codes, or authentication secrets in a PII inventory.
- [ ] Identify whether a data set can initiate or facilitate a transaction if exposed.
- [ ] Restrict who can view full account or taxpayer identifiers; mask them by default.
- [ ] Encrypt exports and use approved secure transfer channels.
- [ ] Review access logs for unusually large exports or access outside normal duties.
- [ ] Keep synthetic documents and transactions in public examples.

## Escalation considerations

Treat exposed authentication material or active payment-access secrets as urgent security issues. Raise criticality when account identifiers are combined with authentication factors, identity documents, transaction history, or large-scale personal financial data. Follow the organization's incident-response process and relevant financial-sector obligations.
