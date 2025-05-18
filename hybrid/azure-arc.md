
# Azure Arc Overview

Azure Arc extends Azure management capabilities to on-premises, multi-cloud, and edge environments.

---

## 1. What Can Azure Arc Manage?

- Physical and virtual servers (Windows/Linux)
- Kubernetes clusters
- SQL servers
- Azure Stack HCI

---

## 2. Server Onboarding

```bash
az connectedmachine connect --resource-group rg1 --name server01 --location eastus
```

- Installs Connected Machine Agent
- Registers the server with Azure

---

## 3. Use Cases

- Centralized policy & RBAC
- Deploy extensions (e.g., Defender for Cloud)
- Inventory and tagging

---

## 4. Governance Integration

- Apply Azure Policy to on-prem resources
- Use Defender for threat detection
