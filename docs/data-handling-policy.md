# Data Handling Policy

## 1. Purpose

This policy describes how contributors should handle information created, referenced, or documented in the Indonesia OSINT & PII Protection Framework. It is designed to keep the repository safe for public release and reduce the chance that project materials become a source of additional exposure.

## 2. Default rule: do not store real sensitive data

The repository should contain documentation, blank templates, public references, diagrams, and synthetic examples, not databases of real personal information.

Do not commit:

- Real NIK/KTP values or images, family-card numbers, NPWP values, or passport numbers.
- Real bank-account or e-wallet details, health information, biometric data, or records relating to children.
- Passwords, API keys, access tokens, private keys, session cookies, or recovery codes.
- Leaked files, breach dumps, credential lists, or private documents.
- Unredacted logs, screenshots, browser exports, or incident evidence containing personal information.

Even if information appears to be publicly accessible, do not reproduce it in the repository unless there is a clear, lawful, documented need and approval. The default for this public educational project is not to publish it.

## 3. Synthetic and anonymized examples

Synthetic examples are preferred. Make them clearly fictional and avoid generating values that could accidentally match real people or credentials.

Use unmistakable placeholders such as:

- `NIK: [REDACTED]`
- `NPWP: [REDACTED]`
- `Phone: [FICTIONAL NUMBER]`
- `Account ID: EXAMPLE-0001`
- `Domain: example.invalid`

Do not assume simple masking makes a dataset anonymous. A record may still identify someone through context, rare attributes, dates, location, or combinations of fields. Remove unnecessary detail and assess re-identification risk before sharing.

## 4. Collection and access

For any authorized internal assessment outside this public repository:

- Document purpose, scope, authorization, and a lawful basis as appropriate.
- Collect the minimum amount of information needed.
- Limit access to named people with a work-related need.
- Use approved storage and transfer mechanisms.
- Do not paste personal data into public issue trackers, pull requests, chat rooms, or public analysis services.
- Use access logs and other safeguards where appropriate to the sensitivity and scale of the assessment.

This repository is not intended to be an evidence vault. Store any necessary evidence in the organization's approved secure case-management system.

## 5. Redaction

Before adding screenshots, reports, or examples, inspect for:

- Names, NIK, KK, NPWP, phone numbers, addresses, emails, and account numbers.
- Document photos, signatures, faces, barcodes, QR codes, and machine-readable zones.
- Passwords, tokens, cookies, private keys, internal hostnames, and confidential URLs.
- Browser tabs, notifications, metadata, filenames, and hidden spreadsheet columns.

Use irreversible redaction. Cropping, drawing a translucent shape over text, or obscuring it in a way that can be reversed is not sufficient. Reopen the exported file and verify the hidden content cannot be recovered or read.

## 6. Retention and deletion

- Keep only what is necessary for the approved purpose.
- Set a retention period before collection for non-public assessment evidence.
- Delete or securely dispose of information when the purpose expires, subject to applicable legal, contractual, and incident-response requirements.
- Do not add personal records to Git history. Deleting a file in a later commit does not remove earlier versions from the repository history.
- If sensitive content is accidentally published, notify the repository owner immediately, restrict or remove access where possible, and follow the platform's guidance for removing sensitive data from repository history. Rotate or revoke exposed credentials immediately. Assume exposed information may already have been copied.

## 7. Incident handling for accidental publication

If sensitive data is committed by mistake:

1. Alert the repository owner and responsible security contact promptly.
2. Remove public access to the affected material where possible.
3. If credentials or secrets are involved, revoke or rotate them without delay.
4. Follow the hosting platform's process for purging sensitive material from history and cached copies where supported.
5. Assess whether individuals, customers, partners, or authorities must be notified under applicable law or contracts. Seek legal/privacy advice when needed.
6. Record the incident without duplicating the exposed values.
7. Review how the content passed review and add preventive checks.

Removing a file from the latest commit alone should not be treated as proof that it has been completely erased.

## 8. Public issue and contribution policy

Do not open public GitHub issues or pull requests containing actual personal data, private records, secrets, or links that expose them unnecessarily. Describe the category and impact using redacted evidence. Contact the repository maintainer privately for sensitive reports and follow any published security-reporting instructions.

## 9. Legal note

This policy is an educational baseline for the repository, not legal advice or a complete organizational data-protection program. Review it against Indonesia's Law No. 27 of 2022 on Personal Data Protection, relevant implementing rules, sector-specific requirements, contractual obligations, and current official guidance.

Official starting point: <https://peraturan.bpk.go.id/Details/229798/uu-no-27->
