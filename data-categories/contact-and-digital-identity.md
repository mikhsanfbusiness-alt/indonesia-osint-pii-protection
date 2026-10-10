# Contact Information & Digital Identity

## Purpose

This category covers contact points, online identifiers, network/device metadata, and authentication material. Credentials and secrets are not always PII by themselves, but they are security-critical and should be inventoried alongside PII because compromise can expose or enable access to personal data.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| Personal contact details | Personal mobile number, email address, home address | P3; raise when combined with identity documents or location history | Phishing, harassment, SIM-swap attempts, doxxing | Limit visibility; mask by default; avoid publishing private contact details |
| Public business contact | Official role-based mailbox, published office contact | P5 when intentionally public and low risk | Spam and phishing | Keep business/public contacts separate from personal contacts; monitor abuse |
| Online account identifiers | Usernames, profile IDs, account recovery hints | P3–P4 depending on linkability | Cross-platform correlation, impersonation, targeted attacks | Minimize public links; review recovery flows; avoid publishing linked account maps for private persons |
| IP/network identifiers | IP addresses, access logs, connection timestamps | P3–P4 depending on context | Activity correlation, location inference, security exposure | Limit log access and retention; aggregate for analytics where possible |
| Device identifiers | Device IDs, advertising IDs, cookie/session identifiers | P2–P4 depending on persistence and linkability | Persistent tracking, account correlation, unauthorized access | Rotate short-lived identifiers where appropriate; minimize collection; protect logs |
| Authentication secrets | Passwords, PINs, OTPs, recovery codes, session cookies, API keys, private keys | P1 if active or usable | Account takeover, unauthorized access, broader data breach | Never publish; use a secrets manager; revoke/rotate if exposed; restrict access and log use |
| Account recovery information | Recovery email/phone, security questions, reset tokens | P1–P2 depending on exploitability | Account recovery abuse and takeover | Avoid weak knowledge-based questions; protect reset links/tokens; monitor account changes |
| Communication content | Private messages, call metadata, recorded conversations | P2–P3 depending on content and scale | Exposure of relationships, sensitive discussions, fraud, reputational harm | Minimize access; obtain appropriate authority/consent; apply retention and deletion controls |

## Assessment checklist

- [ ] Separate public role-based contact details from personal contact data.
- [ ] Do not store actual passwords, OTPs, recovery codes, or live tokens in this catalog or GitHub.
- [ ] Treat accidentally disclosed secrets as an incident: revoke/rotate and investigate potential use.
- [ ] Avoid compiling cross-platform identity maps of private individuals.
- [ ] Restrict and retain network/device logs only for a documented purpose.
- [ ] Redact email addresses, IPs, phone numbers, and tokens in screenshots.

## Escalation considerations

An email address or phone number may be moderate in isolation but much more dangerous when combined with NIK, account recovery details, home address, or a leaked credential. Any live authentication secret should be handled as urgent regardless of the PII score. Do not test credentials on third-party services; use the authorized incident-response procedure.
