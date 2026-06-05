# Certificate Enrolment Protocols (certificate-enrolment-protocols)

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
