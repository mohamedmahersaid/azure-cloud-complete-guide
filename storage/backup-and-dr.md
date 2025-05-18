
# Azure Backup and Disaster Recovery

Azure provides robust BCDR solutions using native services.

---

## 1. Azure Backup

- Agent-based for on-prem or Azure VMs
- App-consistent backup for SQL, SAP, etc.
- Supports daily, weekly, monthly retention

```powershell
Enable-AzRecoveryServicesBackupProtection -Policy $policy -Item $vm
```

---

## 2. Azure Site Recovery (ASR)

- Replicates VMs from:
  - Azure to Azure (cross-region)
  - On-prem to Azure (Hyper-V/VMware)
- Supports multi-VM consistency
- Orchestrates failover/failback

---

## 3. Vaults

- **Recovery Services Vault**: used for backup and ASR
- **Backup Vault**: used for new workloads like AKS

---

## 4. DR Strategy

| Component     | Recommendation |
|---------------|----------------|
| Compute       | Replicate VMs via ASR |
| Network       | Recreate VNet topology with pre-provisioned NSGs |
| Storage       | Use RA-GRS or geo-replication |
| Database      | Use geo-redundant services (e.g., Geo-replicated SQL DB) |

---

## 5. Monitoring and Alerts

- Configure alerts in Backup Vault
- Use Azure Monitor for job-level visibility
- Set up automation for compliance/reporting

---

## 6. Best Practices

- Test restore monthly
- Apply RBAC on backup/ASR permissions
- Encrypt all backup data
