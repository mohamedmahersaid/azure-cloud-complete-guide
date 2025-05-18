
# Microsoft Defender for Cloud Overview

Microsoft Defender for Cloud is a comprehensive CSPM (Cloud Security Posture Management) and workload protection platform for Azure.

---

## 1. Key Capabilities

- Secure Score: security posture insights
- Recommendations: hardening based on Microsoft best practices
- Threat Detection: across VMs, containers, databases, and more
- Integration: with Microsoft Sentinel, Log Analytics

---

## 2. Protection Plans

| Plan                  | Protects                         |
|-----------------------|----------------------------------|
| Servers               | Azure VMs, Arc-enabled servers   |
| Containers            | AKS, registries                  |
| SQL and Databases     | Azure SQL, PostgreSQL, Cosmos DB |
| Storage               | Blob containers                  |
| Key Vault             | Unauthorized access attempts     |

---

## 3. Enable Defender for Cloud

```bash
az security pricing create -n VirtualMachines --tier 'Standard'
```

Or via portal: Defender for Cloud > Environment settings > Enable all plans

---

## 4. Alerts & Integration

- View alerts in Defender dashboard
- Export alerts to Microsoft Sentinel or SIEM
- Set up automation rules (Logic Apps) for response

---

## 5. Best Practices

- Enable auto-provisioning of agents
- Set up email and webhook alerts
- Monitor Secure Score weekly
