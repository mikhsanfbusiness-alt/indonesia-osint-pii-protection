# Other Indonesian Identifiers & Contextual Records

## Purpose

This category captures identifiers not covered elsewhere or whose risk depends strongly on the service and surrounding records. It includes property, utilities, business registration, and other account/reference numbers.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| Property and land records | Land certificate details (for example, SHM/SHGB references), property-tax references such as NOP/PBB, owner and address details | P2–P3 depending on document completeness | Property fraud, targeted scams, location exposure | Restrict full documents; redact owner/ID/address fields; verify requests through trusted channels |
| Utility/service accounts | Electricity customer numbers, water/PDAM customer IDs, internet/customer reference numbers | P3–P4 alone; raise if linked to name/address or account-access data | Account targeting, service impersonation, address correlation | Mask references; limit lookup access; avoid posting bills publicly |
| Business registrations | NIB, corporate NPWP, business licence or registration references | P3–P4 for organization-only records; higher when linked to personal data or beneficial owners | Business impersonation, invoice fraud, exposure of owner/representative details | Distinguish corporate data from personal data; restrict non-public filings and owner details |
| Organization-linked person data | Director, founder, beneficial-owner, representative or authorized signatory details | P2–P3 depending on detail and exposure | Spear-phishing, fraud, unwanted profiling | Share only required public/company information; protect identity-document copies and personal contacts |
| Insurance and membership IDs | Private insurance policy/member numbers, membership records, claims references | P2–P3 depending on linked claims or health data | Claims fraud, identity linking, exposure of sensitive status | Mask IDs; restrict claim documents; separate health and financial details |
| Customer/account references | Internal customer ID, service ticket ID, order number, loyalty account ID | P3–P4 depending on whether it enables lookup | Enumeration, account lookup abuse, correlation across systems | Avoid exposing lookup endpoints; prevent predictable IDs from granting access; rate-limit authorized interfaces |
| Location and property-use details | Home/work location, building access records, delivery instructions, exact geolocation | P2–P3; raise for real-time or repeated tracking | Stalking, burglary risk, profiling, physical safety risk | Limit precision and retention; restrict access; aggregate or redact published examples |
| Other unique identifiers | Any service, registry, membership, or reference number that can be linked to a person | Assess contextually | Re-identification and access to related records | Document purpose, owner, look-up capability, retention, and linkage risks |

## Assessment checklist

- [ ] Determine whether the identifier is issued to an organization, an individual, or both.
- [ ] Check whether the number enables someone to retrieve a record or reset/access an account.
- [ ] Determine whether public registries reveal personal fields when the identifier is used.
- [ ] Separate company records intended for public disclosure from non-public personal information.
- [ ] Redact address, account, ownership, and representative details from examples.
- [ ] Reassess the rank when data is combined with identity or financial information.

## Escalation considerations

A company registration number or utility reference can become high risk if it provides a path to a person's home address, private account, ownership information, or account recovery. Do not assume that a value is safe simply because it is not called a national identity number. Conversely, corporate information intended for public disclosure is not automatically personal data; assess whether it identifies a natural person and what additional information it reveals.
