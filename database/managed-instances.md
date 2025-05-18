
# Azure SQL Managed Instance Overview

SQL Managed Instance provides near full SQL Server engine compatibility in a PaaS environment.

---

## 1. Benefits

- Lift and shift on-prem SQL apps
- No OS management
- Full SQL Server Agent, CLR, linked servers
- VNet integration only (not public)

---

## 2. Key Features

- Automated patching, backups, and HA
- Supports active geo-replication
- Native virtual network support
- Instance-level collation and compatibility levels

---

## 3. Connectivity

- Must be deployed into Azure VNet (subnet required)
- Use Private Link or Azure Bastion for access
- Not accessible over public IP

---

## 4. Backup & Restore

- Point-in-time restore (PITR)
- Long-term backup retention (LTR)

---

## 5. Limitations

- No public endpoint
- Higher cost than single SQL DB
- Startup delay on first access

---

## 6. Use Cases

- Legacy SQL apps needing full instance features
- Apps with SQL Server Agent jobs
- Migration from IaaS SQL

---

## 7. Deployment Sample (CLI)

```bash
az sql mi create --name sqlmi01 --resource-group rg1 --admin-user adminuser --admin-password P@ssword123  --vnet-name myvnet --subnet mi-subnet --license-type BasePrice
```
