# PII Protection Principles

## Purpose

This document provides practical control ideas to pair with an IPCR classification. Controls should be selected based on data criticality, the processing purpose, system architecture, organizational risk, and applicable legal or contractual requirements. This is a starter guide, not a complete compliance checklist.

## Core principles

### 1. Minimize collection

- Collect only fields needed for a documented purpose.
- Avoid collecting full identity-document images or full identifiers where a partial value or verification result is sufficient.
- Reassess whether old records still need to be retained.

### 2. Limit access

- Grant access on a least-privilege, need-to-know basis.
- Separate ordinary business access from bulk export and administration permissions.
- Use multi-factor authentication for administrative and sensitive-data access where appropriate.
- Review access when roles change and remove it promptly when no longer required.

### 3. Protect data at rest and in transit

- Use approved encryption for stored data and network transfers.
- Store keys separately from the protected data and limit key access.
- Avoid sending personal data through unapproved chat, email, or file-sharing services.
- Do not put secrets or production personal data in source control, issue trackers, screenshots, or demo files.

### 4. Mask and redact

- Mask identifiers in routine user interfaces and reports.
- Show only the minimum characters necessary for a legitimate task.
- Redact identity documents, signatures, barcodes, QR codes, addresses, account numbers, and metadata before sharing screenshots.
- Verify redaction by checking that hidden content cannot be recovered from the file.

### 5. Control exports and copies

- Restrict bulk exports and maintain audit logs for high-risk operations.
- Use approved, time-limited sharing methods.
- Remove local downloads and temporary copies when no longer necessary.
- Avoid creating duplicate datasets for convenience.

### 6. Set retention and disposal rules

- Define retention periods based on purpose, operational need, and applicable obligations.
- Delete or securely dispose of data when the approved retention period ends, unless a valid hold or other requirement applies.
- Include backups, exports, and third-party copies in the disposal process where feasible and appropriate.

### 7. Monitor and prepare

- Log access to sensitive records and monitor unusual query or export patterns.
- Maintain an incident response path with clearly assigned roles.
- Test backup restoration and incident procedures.
- Train staff to recognize phishing, social engineering, and inappropriate data handling.

### 8. Manage vendors and sharing

- Identify third parties that process or receive personal data.
- Define approved purposes, security expectations, retention, incident notification, and deletion responsibilities in appropriate agreements.
- Review data transfers and access paths periodically.

## Suggested minimum controls by IPCR level

| IPCR level | Example safeguards |
|---|---|
| **P1 — Critical** | Strongly restricted access; encryption; MFA for privileged access; robust logging and alerting; tightly controlled exports; frequent review; tested response plan |
| **P2 — Very High** | Role-based access; encryption; masking by default; approval for bulk export; access reviews; retention controls |
| **P3 — High** | Role-based access; secure storage and transfers; export monitoring; defined retention; periodic access reviews |
| **P4 — Moderate** | Standard access controls; approved sharing; minimize publication; review linkability and bulk access |
| **P5 — Low** | Basic safeguards remain in place; confirm that publication is intentional and does not reveal additional nonpublic details |

These are suggested baselines, not guarantees of compliance or security. A lower-ranked dataset may require stronger controls because of context or system risk.

## Indonesia-specific data examples

- **NIK/KTP and KK:** limit full-value access, mask values in routine workflows, and avoid storing document images unless needed.
- **NPWP and tax records:** restrict to authorized finance/tax roles and secure related documents and exports.
- **Vehicle plate, STNK, and BPKB data:** prevent unnecessary linkage between vehicle information and owner identities or home/work locations.
- **BPJS, health, and employment records:** restrict access by role and prevent broad access to health, payroll, or benefits details.
- **Phone numbers and personal email addresses:** limit bulk exports and monitor for misuse in customer or employee lists.
- **Credentials and tokens:** never store in public documentation; use a secret manager and revoke exposed secrets promptly.

## Public GitHub project rules

This repository should contain documentation, templates, synthetic examples, and properly redacted screenshots only. Do not commit real NIK, KK numbers, tax or bank records, identity-document images, leaked databases, passwords, tokens, or sensitive incident evidence.
