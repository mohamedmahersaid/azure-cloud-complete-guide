
# Azure Landing Zone Blueprint

An Azure Landing Zone is a foundational architecture for enabling cloud workloads at scale.

---

## 1. Key Landing Zone Components

| Component          | Description |
|-------------------|-------------|
| Management Groups | Hierarchical structure for governance |
| Subscriptions      | Separate environments or business units |
| Azure Policies     | Enforce guardrails |
| RBAC & Security Groups | Control access based on roles |
| Virtual Networks   | Hub and spoke or mesh model |
| Logging & Monitoring | Azure Monitor, Log Analytics, Diagnostic Settings |

---

## 2. Recommended Topology

- **Management Group Hierarchy**:
```
Tenant Root Group
├── Platform
│   ├── Connectivity
│   └── Identity
├── Landing Zones
│   ├── Corp
│   ├── Online
└── Sandbox
```

- **Networking**: Hub-and-spoke with Firewall in Hub
- **Identity**: Centralized Azure AD with hybrid connect (if applicable)

---

## 3. Tools

- Bicep or Terraform templates
- Azure Blueprints (or Template Specs)
- GitHub Actions / Azure DevOps pipelines

---

## 4. Governance and Policy

Apply policies for:
- Allowed regions
- SKU restrictions
- Tag enforcement
- Security Center configuration

---

## 5. Monitoring & Management

- Enable Defender for Cloud
- Route all logs to centralized workspace
- Define alerting thresholds per workload

---

## 6. Reference Architectures

- [CAF Ready Landing Zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
