
# Azure Storage Accounts Overview

Azure Storage offers scalable, secure, and cost-effective cloud storage for all workloads.

---

## 1. Storage Account Types

| Type                  | Use Case                     |
|-----------------------|------------------------------|
| General-purpose v2    | Most common, supports all services |
| Blob Storage          | Optimized for blob only      |
| FileStorage           | Premium file shares          |
| BlockBlobStorage      | Premium blob workloads       |

---

## 2. Storage Services

- **Blob**: Unstructured data, hot/cool/archive tiers
- **File**: SMB file shares
- **Queue**: Messaging between services
- **Table**: NoSQL structured storage
- **Disk**: OS and data disks for VMs

---

## 3. Redundancy Options

| Redundancy | Description                      |
|------------|----------------------------------|
| LRS         | Locally redundant (within zone) |
| ZRS         | Zone redundant (across zones)   |
| GRS         | Geo redundant (secondary region)|
| RA-GRS      | Read-access geo redundant       |

---

## 4. Secure Access

- Use **Azure AD** for blob/file access
- SAS tokens for scoped temporary access
- Enable **Private Endpoint** to restrict to VNet
- Encrypt data at rest with platform-managed or customer-managed keys

---

## 5. Cost Optimization

- Choose access tier (Hot, Cool, Archive) per blob
- Use Lifecycle Management rules to transition data
- Monitor metrics via Azure Monitor

---

## 6. Monitoring

- Enable diagnostic settings
- Send metrics to Log Analytics
- Review storage logs in Storage Explorer
