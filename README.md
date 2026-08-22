# Varonis (varonis)

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

Varonis is a pioneer in data security and analytics, specializing in software for data security, governance, threat detection and response. The company provides solutions for protecting enterprise data across cloud and on-premises environments including data classification, access governance, behavioral threat detection, and automated remediation.

**APIs.json:** [https://www.varonis.com](https://www.varonis.com)

## Tags

- Cloud Security
- Compliance
- Data Analytics
- Data Governance
- Data Security
- Threat Detection

## Timestamps

- **Created:** 2025
- **Modified:** 2026-05-19

## APIs

### Varonis DatAlert API

API for accessing threat detection and incident response capabilities from Varonis DatAlert. Provides endpoints for retrieving alerts, managing alert status, adding notes to alerts, and accessing alerted events for investigation and threat hunting. The DatAlert API enables integration with SIEM and SOAR platforms for centralized security operations.

- **Human URL:** [https://www.varonis.com/products/datalert](https://www.varonis.com/products/datalert)
- **Base URL:** `https://api.varonis.com/datalert`

#### Tags

- Incident Response
- Security Alerts
- Threat Detection

#### Properties

- [Documentation](https://docs.varonis.com/api/datalert)
- [OpenAPI](openapi/varonis-datalert-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/varonis-datalert.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/varonis-datalert.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](https://docs.varonis.com/api/authentication)
- [JSON Schema](json-schema/varonis-datalert-alert-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/varonis-datalert-alerted-event-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/varonis-datalert-threat-model-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/varonis-datalert-alert-structure.json)
- [JSON Structure](json-structure/varonis-datalert-alerted-event-structure.json)
- [Example](examples/varonis-datalert-alert-example.json)
- [Example](examples/varonis-datalert-alerted-event-example.json)

### Varonis Data Security Platform API

API for integrating with Varonis Data Security Platform to manage data security policies, access permissions, and threat detection.

- **Human URL:** [https://www.varonis.com/products/data-security-platform](https://www.varonis.com/products/data-security-platform)
- **Base URL:** `https://api.varonis.com`

#### Tags

- Access Control
- Data Security
- Permissions

#### Properties

- [Documentation](https://docs.varonis.com/api)
- [Authentication](https://docs.varonis.com/api/authentication)
- [Postman Collection](collections/varonis-datalert.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/varonis-datalert.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Varonis DataPrivilege API

REST and SOAP API for integrating Varonis DataPrivilege with IAM and ITSM solutions. Enables synchronization of managed data, execution and reporting on access requests and access control changes, and automation of entitlement reviews and self-service access workflows.

- **Human URL:** [https://www.varonis.com/products/dataprivilege](https://www.varonis.com/products/dataprivilege)
- **Base URL:** `https://api.varonis.com`

#### Tags

- Access Governance
- Entitlement Reviews
- Identity Management
- Self-Service Access

#### Properties

- [Documentation](https://www.varonis.com/blog/introducing-gdpr-patterns-and-dataprivilege-api)
- [Postman Collection](collections/varonis-datalert.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/varonis-datalert.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Varonis MCP Server

Model Context Protocol server that interfaces with Varonis APIs, allowing AI clients such as ChatGPT, Claude, and GitHub Copilot to access and orchestrate the Varonis Data Security Platform using natural language. Enables complex workflows including alert retrieval, access remediation, and compliance reporting.

- **Human URL:** [https://www.varonis.com/blog/mcp-server](https://www.varonis.com/blog/mcp-server)
- **Base URL:** `https://api.varonis.com`

#### Tags

- AI Integration
- Automation
- MCP
- Natural Language

#### Properties

- [Documentation](https://www.varonis.com/blog/mcp-server)
- [SDK](https://www.npmjs.com/package/@varonis/mcp)
- [Postman Collection](collections/varonis-datalert.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/varonis-datalert.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [LinkedIn](https://www.linkedin.com/company/varonis)
- [Portal](https://www.varonis.com/developers)
- [Website](https://www.varonis.com)
- [Support](https://www.varonis.com/resources/support)
- [Blog](https://www.varonis.com/blog)
- [Privacy Policy](https://www.varonis.com/trust/privacy)
- [Terms of Service](https://www.varonis.com/terms)
- [Status Page](https://status.varonis.com)
- [Changelog](https://www.varonis.com/platform/changelog)
- [Security](https://www.varonis.com/trust/security)
- [Login](https://my.varonis.io/)
- [Sign Up](https://help.varonis.com/s/article/WDOC-2305)
- [Help Center](https://help.varonis.com/s/)
- [Trust Center](https://www.varonis.com/trust)
- [Integrations](https://www.varonis.com/security-ecosystem-integrations)
- [Training](https://www.varonis.com/product-training)
- [Content Library](https://www.varonis.com/resources)
- [GitHub Organization](https://github.com/varonis)
- [Partner Portal](https://partners.varonis.com/)
- [Spectral Rules](rules/varonis-spectral-rules.yml)
- [Vocabulary](vocabulary/varonis-vocabulary.yaml)
- [JSON-LD](json-ld/varonis-datalert-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
**URL:** https://apievangelist.com
