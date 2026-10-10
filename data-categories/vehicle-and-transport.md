# Vehicle, Driving & Transport Records

## Purpose

This category covers identifiers and records associated with vehicles, drivers, ownership, registration, and transport activity in Indonesia.

## Data catalog

| Data category | Examples of fields | Suggested baseline | Main risks | Baseline safeguards |
|---|---|---:|---|---|
| Vehicle registration plate | Nomor polisi / nopol | P4 alone; P2–P3 when linked to owner/address or movement | Identification of owner through combined sources, stalking, targeted harassment | Avoid publishing linked owner details; limit search access in internal systems |
| Registration documents | STNK data, registration status, vehicle details, owner data where present | P2–P3 depending on fields | Impersonation, document misuse, exposure of owner details | Restrict document access; redact personal fields; avoid public uploads |
| Ownership evidence | BPKB and related ownership records | P2 | Ownership fraud, identity impersonation, financial/social engineering risks | Store securely; strictly limit copying and exports; log retrieval |
| Driving licence | SIM number, licence category and validity, personal fields | P2–P3 | Identity impersonation, profiling, fraud | Minimize collection; mask number; restrict to legitimate operational needs |
| Transport and journey records | Ride-hailing history, trip timestamps, pick-up/drop-off points, fleet/driver schedules | P2–P3; raise if detailed or real-time | Location tracking, stalking, personal routine inference | Limit precision and retention; restrict operational access; aggregate when reporting |
| Fleet/telematics records | Vehicle identifiers, GPS history, driver identifiers, device data | P2–P3 depending on linkage | Employee tracking, location profiling, operational security exposure | Purpose-bound collection; access logging; protect exports and dashboards |

## Assessment checklist

- [ ] Determine whether the plate or vehicle record is linked to an identifiable owner or driver.
- [ ] Treat exact location and time history as higher risk than a static vehicle attribute.
- [ ] Avoid attempts to identify private vehicle owners using unofficial or restricted databases.
- [ ] Remove plate numbers, faces, document details, and precise route data from public screenshots.
- [ ] Limit retention of journey and telemetry information to the documented purpose.
- [ ] Use fictional plates and routes in examples.

## Escalation considerations

A plate number in isolation may present a different risk from a plate number combined with a named owner, home address, recurring travel routes, and identity documents. Raise the ranking when the combination enables tracking, stalking, or direct impersonation. Do not infer wrongdoing from the presence of a plate number or unverified crowdsourced claims.
