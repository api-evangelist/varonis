# Varonis (varonis)
Varonis is a pioneer in data security and analytics, specializing in software for data security, governance, threat detection and response. The company provides solutions for protecting enterprise data across cloud and on-premises environments including data classification, access governance, behavioral threat detection, and automated remediation.

**URL:** [https://www.varonis.com](https://www.varonis.com)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Cloud Security, Compliance, Data Analytics, Data Governance, Data Security, Threat Detection

## Timestamps

- **Created:** 2025
- **Modified:** 2026-05-03

## APIs

### Varonis DatAlert API
API for accessing threat detection and incident response capabilities from Varonis DatAlert. Provides endpoints for retrieving alerts, managing alert status, adding notes to alerts, and accessing alerted events for investigation and threat hunting.

**Human URL:** [https://www.varonis.com/products/datalert](https://www.varonis.com/products/datalert)

#### Tags:

 - Incident Response, Security Alerts, Threat Detection

#### Properties

- [Documentation](https://docs.varonis.com/api/datalert)
- [OpenAPI](openapi/varonis-datalert-openapi.yml)
- [Authentication](https://docs.varonis.com/api/authentication)
- [JSONSchema - Alert Schema](json-schema/varonis-datalert-alert-schema.json)
- [JSONSchema - Alerted Event Schema](json-schema/varonis-datalert-alerted-event-schema.json)
- [JSONStructure - Alert Structure](json-structure/varonis-datalert-alert-structure.json)
- [Example - Alert Example](examples/varonis-datalert-alert-example.json)

### Varonis Data Security Platform API
API for integrating with Varonis Data Security Platform to manage data security policies, access permissions, and threat detection.

**Human URL:** [https://www.varonis.com/products/data-security-platform](https://www.varonis.com/products/data-security-platform)

#### Tags:

 - Access Control, Data Security, Permissions

#### Properties

- [Documentation](https://docs.varonis.com/api)
- [Authentication](https://docs.varonis.com/api/authentication)

### Varonis DataPrivilege API
REST and SOAP API for integrating Varonis DataPrivilege with IAM and ITSM solutions. Enables access request automation, entitlement reviews, and self-service access workflows.

**Human URL:** [https://www.varonis.com/products/dataprivilege](https://www.varonis.com/products/dataprivilege)

#### Tags:

 - Access Governance, Entitlement Reviews, Identity Management, Self-Service Access

#### Properties

- [Documentation](https://www.varonis.com/blog/introducing-gdpr-patterns-and-dataprivilege-api)

### Varonis MCP Server
Model Context Protocol server enabling AI clients (Claude, ChatGPT, GitHub Copilot) to access and orchestrate the Varonis Data Security Platform using natural language.

**Human URL:** [https://www.varonis.com/blog/mcp-server](https://www.varonis.com/blog/mcp-server)

#### Tags:

 - AI Integration, Automation, MCP, Natural Language

#### Properties

- [Documentation](https://www.varonis.com/blog/mcp-server)
- [SDK - MCP Server npm Package](https://www.npmjs.com/package/@varonis/mcp)

## Common Properties

- [Portal](https://www.varonis.com/developers)
- [Website](https://www.varonis.com)
- [Support](https://www.varonis.com/resources/support)
- [Blog](https://www.varonis.com/blog)
- [PrivacyPolicy](https://www.varonis.com/trust/privacy)
- [TermsOfService](https://www.varonis.com/terms)
- [StatusPage](https://status.varonis.com)
- [ChangeLog](https://www.varonis.com/platform/changelog)
- [TrustCenter](https://www.varonis.com/trust)
- [HelpCenter](https://help.varonis.com/s/)
- [GitHubOrganization](https://github.com/varonis)
- [Integrations](https://www.varonis.com/security-ecosystem-integrations)
- [Training](https://www.varonis.com/product-training)
- [PartnerPortal](https://partners.varonis.com/)

## Features

| Name | Description |
|------|-------------|
| Behavioral Threat Detection | AI-powered detection of abnormal user and data access behavior using DatAlert threat models aligned to MITRE ATT&CK. |
| Data Classification | Automated sensitive data discovery and classification across cloud and on-premises data stores. |
| Access Governance | DataPrivilege workflow automation for entitlement reviews, access requests, and permission remediation. |
| Forensic Investigation | Detailed event-level forensics including file access, permission changes, and login activity for incident investigation. |
| SIEM and SOAR Integration | REST API integration with SIEM platforms (Splunk, QRadar, Sentinel) and SOAR platforms (XSOAR, Phantom) for automated response. |
| AI-Assisted Security (MCP) | Model Context Protocol server enabling natural language security operations with Claude, ChatGPT, and GitHub Copilot. |
| Compliance Reporting | Built-in reporting for GDPR, HIPAA, PCI-DSS, SOX, and other compliance frameworks. |
| Cloud Security Posture | Data security posture management for Microsoft 365, AWS, Azure, and Google Cloud environments. |

## Use Cases

| Name | Description |
|------|-------------|
| Insider Threat Detection | Detect and respond to abnormal access patterns that indicate potential insider threats or compromised accounts. |
| Ransomware Detection | Identify ransomware activity through mass file access, renaming, and encryption patterns. |
| Data Breach Investigation | Investigate potential data breaches using forensic event trails to determine scope and blast radius. |
| Privileged Access Review | Automate periodic entitlement reviews to ensure least-privilege access to sensitive data. |
| Compliance Audit | Generate audit-ready reports demonstrating data access controls for regulatory frameworks. |
| SOAR Automation | Integrate alert triage and remediation into automated playbooks via the DatAlert REST API. |
| AI-Driven Security Operations | Use the Varonis MCP Server to enable AI assistants to query alerts, investigate events, and execute remediation. |

## Integrations

| Name | Description |
|------|-------------|
| Microsoft Sentinel | Ingest Varonis alerts and events into Microsoft Sentinel for correlation and automated response. |
| Splunk | Stream DatAlert events to Splunk via the official Varonis App for Splunk SIEM integration. |
| IBM QRadar | Forward Varonis DatAlert events to QRadar using the official integration guide. |
| CrowdStrike Falcon | Enrich endpoint threat data with Varonis user and data access context. |
| ServiceNow | Create and manage security incident tickets in ServiceNow from Varonis alerts. |
| Palo Alto XSOAR | Automate alert triage and remediation workflows using the Varonis XSOAR integration. |
| Microsoft 365 | Monitor and protect SharePoint, OneDrive, Exchange, and Teams data natively. |
| AWS | Data security posture management for S3, RDS, and other AWS data services. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Varonis DatAlert API](openapi/varonis-datalert-openapi.yml)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Varonis DatAlert API](capabilities/shared/datalert.yaml) — 6 operations for threat detection and alert management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Threat Detection and Response](capabilities/threat-detection-response.yaml) | DatAlert | 6 | SOC Analyst |

## Vocabulary

- [Varonis Vocabulary](vocabulary/varonis-vocabulary.yaml) — Unified taxonomy mapping 3 resources, 6 actions, 1 workflow, and 1 persona across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Varonis Spectral Rules](rules/varonis-spectral-rules.yml) — 30 rules across 9 categories enforcing Varonis API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
