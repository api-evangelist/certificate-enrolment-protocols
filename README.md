# Certificate Enrolment Protocols (certificate-enrolment-protocols)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Certificate Enrolment Protocols are the interoperable standards that automate the lifecycle operations of requesting, issuing, renewing, and revoking X.509 digital certificates between Certificate Authorities (CAs), Registration Authorities (RAs), and end entities. The four major protocols in active deployment are ACME (RFC 8555, widely adopted via Let's Encrypt and cert-manager for web PKI), SCEP (legacy Simple Certificate Enrollment Protocol widely supported in network devices and MDM), EST (RFC 7030, Enrollment over Secure Transport for modern HTTPS-capable devices), and CMP (RFC 4210 / RFC 9480, Certificate Management Protocol for enterprise PKI and industrial automation). This index tracks the specifications, reference implementations, and supporting infrastructure for each.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/certificate-enrolment-protocols/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/certificate-enrolment-protocols/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- ACME
- Automation
- CMP
- Certificates
- Cryptography
- EST
- IETF
- Let's Encrypt
- PKI
- RFC
- Renewal
- SCEP
- Security
- Standards

## Timestamps

- **Created:** 2025-01-01
- **Modified:** 2026-05-19

## APIs

### ACME - Automatic Certificate Management Environment (RFC 8555)

ACME is an IETF standard defined in RFC 8555 that automates the interactions between CAs and web servers for validating domain control (http-01, dns-01, tls-alpn-01 challenges), issuing, renewing, and revoking X.509 certificates. ACME is the protocol behind Let's Encrypt, ZeroSSL, and most cloud CAs, and is implemented in clients including certbot, acme.sh, Lego, win-acme, and cert-manager.

- **Human URL:** [https://datatracker.ietf.org/doc/html/rfc8555](https://datatracker.ietf.org/doc/html/rfc8555)

#### Tags

- ACME
- Let's Encrypt
- RFC 8555
- Web PKI

#### Properties

- [Specification](https://datatracker.ietf.org/doc/html/rfc8555)
- [Reference Implementation](https://letsencrypt.org/docs/)
- [Source Code](https://github.com/letsencrypt/boulder)
- [Integration](https://cert-manager.io/docs/configuration/acme/)
- [OpenAPI](openapi/certificate-enrolment-protocols-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/certificate-enrolment-protocols.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/certificate-enrolment-protocols.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SCEP - Simple Certificate Enrollment Protocol

SCEP is a PKCS#7 / PKCS#10-based certificate enrollment protocol originally developed by Cisco in the late 1990s and standardized as informational RFC 8894. Despite its age, SCEP remains the dominant enrollment protocol for routers, switches, VPN concentrators, and mobile device management platforms (Apple MDM, Microsoft Intune).

- **Human URL:** [https://datatracker.ietf.org/doc/html/rfc8894](https://datatracker.ietf.org/doc/html/rfc8894)

#### Tags

- IoT
- MDM
- Network Devices
- SCEP

#### Properties

- [Specification](https://datatracker.ietf.org/doc/html/rfc8894)
- [Overview](https://en.wikipedia.org/wiki/Simple_Certificate_Enrollment_Protocol)
- [Source Code](https://github.com/micromdm/scep)
- [Postman Collection](collections/certificate-enrolment-protocols.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/certificate-enrolment-protocols.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### EST - Enrollment over Secure Transport (RFC 7030)

EST provides HTTPS-based certificate enrollment over TLS, using mutual authentication or TLS with certificate-less client authentication to establish a secure channel before PKCS#10 enrollment. EST targets modern HTTPS-capable IoT and network devices that need simpler deployment than CMP but more secure transport than SCEP.

- **Human URL:** [https://datatracker.ietf.org/doc/html/rfc7030](https://datatracker.ietf.org/doc/html/rfc7030)

#### Tags

- EST
- IoT
- RFC 7030
- TLS

#### Properties

- [Specification](https://datatracker.ietf.org/doc/html/rfc7030)
- [Updates](https://datatracker.ietf.org/doc/html/rfc8951)
- [Source Code](https://github.com/cisco/libest)
- [Postman Collection](collections/certificate-enrolment-protocols.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/certificate-enrolment-protocols.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CMP - Certificate Management Protocol (RFC 4210 / RFC 9480)

CMP provides comprehensive certificate lifecycle management including initialization, key update, revocation, cross-certification, and recovery for enterprise and industrial PKI environments. CMP messages carry their own cryptographic protection independent of the transport and are commonly used in 3GPP mobile networks, industrial automation, and telco infrastructure.

- **Human URL:** [https://datatracker.ietf.org/doc/html/rfc4210](https://datatracker.ietf.org/doc/html/rfc4210)

#### Tags

- CMP
- Enterprise PKI
- Industrial
- RFC 4210
- RFC 9480

#### Properties

- [Specification](https://datatracker.ietf.org/doc/html/rfc4210)
- [Lightweight C M P](https://datatracker.ietf.org/doc/html/rfc9480)
- [Source Code](https://github.com/mpeylo/cmpclient)
- [Postman Collection](collections/certificate-enrolment-protocols.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/certificate-enrolment-protocols.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### cert-manager (Kubernetes ACME Client)

cert-manager is a CNCF Graduated Kubernetes controller that acts as an ACME, Vault, Venafi, and CA client to automatically issue and renew certificates declaratively for workloads and Ingress/Gateway API objects.

- **Human URL:** [https://cert-manager.io/](https://cert-manager.io/)

#### Tags

- ACME
- CNCF
- Client
- Kubernetes

#### Properties

- [Website](https://cert-manager.io/)
- [Documentation](https://cert-manager.io/docs/configuration/acme/)
- [Source Code](https://github.com/cert-manager/cert-manager)
- [Postman Collection](collections/certificate-enrolment-protocols.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/certificate-enrolment-protocols.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Certbot (ACME Reference Client)

Certbot, maintained by the Electronic Frontier Foundation (EFF), is the reference ACME client used to obtain and renew Let's Encrypt and other ACME CA certificates on web and mail servers with a focus on automation and Apache/Nginx plugin support.

- **Human URL:** [https://certbot.eff.org/](https://certbot.eff.org/)

#### Tags

- ACME
- Certbot
- EFF
- Let's Encrypt

#### Properties

- [Website](https://certbot.eff.org/)
- [Documentation](https://eff-certbot.readthedocs.io/)
- [Source Code](https://github.com/certbot/certbot)
- [Postman Collection](collections/certificate-enrolment-protocols.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/certificate-enrolment-protocols.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://en.wikipedia.org/wiki/Certificate_enrollment)
- [I E T F](https://datatracker.ietf.org/)
- [Lets Encrypt](https://letsencrypt.org/)
- [Cert Manager](https://cert-manager.io/)
- [Certbot](https://certbot.eff.org/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
