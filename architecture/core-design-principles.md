
# Core Azure Architecture Design Principles

These principles guide the design of scalable, secure, and high-performing Azure solutions.

---

## 1. Subscription and Tenant Strategy

- Use multiple subscriptions for isolation (prod/dev/test)
- Map subscriptions to business units or workloads
- Apply Management Groups for unified policy enforcement

---

## 2. Resource Organization

- Use Resource Groups to organize logically related resources
- Follow naming conventions: `rg-appname-env-region`
- Apply tags: `Environment`, `Owner`, `CostCenter`

---

## 3. Resilience and Redundancy

- Use Availability Zones for zonal resilience
- Deploy geo-redundant services (GZRS, paired regions)
- Implement Azure Site Recovery (ASR) and Backup

---

## 4. Security by Design

- Zero Trust: verify explicitly, use least privilege
- Centralized identity with Azure AD
- Secure secrets via Key Vault
- Apply NSGs, ASGs, and firewalls

---

## 5. Cost Management

- Use Azure Reservations for VMs and databases
- Monitor with Cost Management + Azure Advisor
- Turn off unused resources with automation

---

## 6. Network Design

- Hub-and-Spoke topology for large networks
- Use VNet peering and Private Endpoints
- Secure ingress via Azure Firewall or App Gateway

---

## 7. Observability

- Centralize logs in Log Analytics
- Enable diagnostic settings for every resource
- Use Azure Monitor, Alerts, and Workbooks

---

## 8. Compliance and Governance

- Use Azure Policy for control enforcement
- Set budgets and alerts
- Apply RBAC and role-scoped access

---

## 9. Automation

- Use Bicep/Terraform/ARM for deployment
- Automate with Azure DevOps or GitHub Actions

---

## 10. Reference

- [Microsoft Cloud Adoption Framework](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/)
