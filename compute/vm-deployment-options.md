
# Azure Virtual Machine Deployment Options

Azure provides several ways to deploy, scale, and manage virtual machines efficiently.

---

## 1. Deployment Tools

| Tool          | Description |
|---------------|-------------|
| Azure Portal  | Manual deployment, good for one-offs |
| Azure CLI     | Scripting and automation |
| ARM/Bicep     | Infrastructure as code, repeatable |
| Terraform     | Cross-cloud automation |
| Azure DevOps  | CI/CD pipeline integration |

---

## 2. VM Sizing and Types

- Choose size based on CPU, RAM, disk IOPS, NIC count
- Families:
  - **B-Series**: Burst workloads
  - **D/E-Series**: General purpose and memory optimized
  - **F-Series**: Compute optimized
  - **NV/NC**: GPU workloads

---

## 3. OS Options

- Windows Server, Ubuntu, RHEL, SUSE, CentOS, Oracle
- Azure Marketplace supports thousands of custom images

---

## 4. Availability and Redundancy

- **Availability Sets**: VM separation across fault and update domains
- **Availability Zones**: Physical datacenter isolation (use for SLA 99.99%)
- **Scale Sets**: Autoscale identical VMs based on rules

---

## 5. Automation Snippet (Bicep)

```bicep
resource vm 'Microsoft.Compute/virtualMachines@2022-11-01' = {
  name: 'vm-demo'
  location: resourceGroup().location
  properties: {
    hardwareProfile: {
      vmSize: 'Standard_D2s_v3'
    }
    osProfile: {
      adminUsername: 'azureadmin'
      adminPassword: 'P@ssw0rd123'
    }
    networkProfile: { ... }
    storageProfile: { ... }
  }
}
```

---

## 6. Best Practices

- Use managed disks
- Enable boot diagnostics
- Tag resources for cost control and management
