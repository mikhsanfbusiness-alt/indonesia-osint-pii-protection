# Glossary

This glossary explains terms used throughout the project. It is a practical reference, not a complete legal dictionary. Whether information qualifies as personal data depends on context, identifiability, and applicable law.

## General security and privacy terms

| Term | Meaning in this project |
|---|---|
| **PII** | Personally Identifiable Information; a common international term for information that identifies or can help identify a person. Indonesian law uses the term *Data Pribadi*. |
| **Data Pribadi** | Under Indonesia's Law No. 27 of 2022, information about an identified or identifiable natural person, alone or combined with other information, through electronic or non-electronic systems. Consult the official text for the exact legal definition. |
| **OSINT** | Open-source intelligence: collecting and analyzing information from publicly accessible or otherwise lawfully available sources for a defined purpose. |
| **Data exposure** | A condition in which information becomes accessible or visible outside its intended access boundary. Exposure does not always prove that the information was accessed or misused. |
| **Data breach** | An incident involving unauthorized access, disclosure, alteration, loss, or other compromise of data. The precise definition and notification duties depend on applicable rules and context. |
| **IOC** | Indicator of Compromise: an observable artifact associated with potentially malicious activity, such as a domain, file hash, IP address, or URL. An IOC requires context and is not automatically proof of maliciousness. |
| **PII inventory** | A record of data categories an organization processes, the purposes, systems, ownership, access, retention, and safeguards. Avoid putting the raw values of identifiers in an inventory. |
| **Data minimization** | Limiting processing to information necessary for the defined purpose. |
| **Redaction** | Irreversibly hiding sensitive information in an artifact before sharing it. |
| **Synthetic data** | Artificially created example data that does not represent a real person or real confidential record. |
| **Confidence** | The level of support for a finding, based on evidence quality, reliability, and limitations. |
| **Risk** | A combination of the likelihood of an event and its potential consequences; different organizations may adopt different formal definitions. |
| **IPCR** | Indonesia PII Criticality Ranking: the proposed, non-official prioritization model defined by this project. |

## Indonesia-specific identifiers and records

| Term | Description and handling note |
|---|---|
| **NIK** | Nomor Induk Kependudukan, a population identification number. Treat as highly sensitive in this framework; do not include actual values in public examples. |
| **KTP-el / KTP** | Indonesian identity card (electronic identity card in the case of KTP-el). Images can contain multiple personal attributes and machine-readable details. |
| **KK** | Kartu Keluarga, a family-card record that can reveal household and family relationships. Protect the document and all listed members' information. |
| **NPWP** | Nomor Pokok Wajib Pajak, a tax identification number. Treatment and linkage with NIK can depend on current tax rules and the person's circumstances; verify current official guidance. |
| **Nomor polisi / nopol** | Vehicle registration plate number. Alone it may have limited identifying context; when linked to ownership records, location, or other information, risk can increase. |
| **STNK** | Surat Tanda Nomor Kendaraan, vehicle registration certificate. May include details that link a vehicle to a registered owner. |
| **BPKB** | Buku Pemilik Kendaraan Bermotor, vehicle ownership document. Handle ownership details as sensitive. |
| **SIM** | Surat Izin Mengemudi, driving licence. Images and associated information may expose identity details. |
| **Paspor** | Passport and passport number. Passport images can expose identity and travel-document details. |
| **BPJS Kesehatan** | Indonesia's national health insurance program. Membership information can be sensitive when linked to an identifiable person or health service use. |
| **BPJS Ketenagakerjaan / KPJ** | Employment social-security program and commonly referenced participant or membership number. Verify terminology in the specific record or system. |
| **NIP** | Nomor Induk Pegawai, often used as an employee identifier in government employment contexts. Context matters when assessing whether it identifies a person. |
| **NISN** | Nomor Induk Siswa Nasional, a national student identification number. Take extra care because records may involve minors. |
| **NIM** | Nomor Induk Mahasiswa, a university student number assigned by an institution. |
| **NIB** | Nomor Induk Berusaha, business identification number. Usually associated with a business; it may still link to a sole proprietor or other identifiable person depending on context. |
| **NPWP badan** | Tax identification associated with a legal entity or organization. It is not automatically personal data, but related documents may contain personal or confidential business information. |
| **Nomor rekening** | Bank account number. Its sensitivity and risk depend on associated information, transaction context, and whether authentication or financial data is also exposed. |
| **Nomor HP** | Mobile phone number. May be a personal identifier and can support phishing or account-recovery attacks when combined with other data. |
| **Token / API key / private key** | Credentials or cryptographic secrets used to authenticate or authorize access to systems. If exposed, revoke or rotate them promptly. These are security secrets, whether or not they are personal data. |

## IPCR tiers

| Tier | Meaning |
|---|---|
| **P1: Critical** | Immediate escalation and coordinated response are generally warranted. |
| **P2: Very High** | Urgent remediation and management visibility are generally warranted. |
| **P3: High** | Prompt remediation with a clear owner and deadline. |
| **P4: Moderate** | Planned remediation and periodic review. |
| **P5: Low** | Maintain appropriate controls and reassess when context changes. |

These tiers are project-specific. They are not official government data classifications, and the same data category can receive different operational scores depending on context.

## Official legal reference

- Indonesia, Law No. 27 of 2022 on Personal Data Protection: <https://peraturan.bpk.go.id/Details/229798/uu-no-27->
- Ministry of Communication and Digital Affairs legal database: <https://jdih.komdigi.go.id/produk_hukum/view/id/832/t/undangundang%2Bnomor%2B27%2Btahun%2B2022>
