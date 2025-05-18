
# Azure Virtual Network (VNet) Design

Virtual Networks (VNets) are the foundation of Azure networking, enabling secure and isolated environments.

---

## 1. Address Space Planning

- Use private IP ranges (RFC1918): 10.x, 172.16.x, 192.168.x
- Avoid overlapping address spaces across VNets and with on-prem
- Plan for growth: /16 or /20 address space, subnet into smaller blocks

---

## 2. Subnet Strategy

- Separate subnets by workload type (Web, DB, App)
- Delegate subnets to services (e.g., Azure Bastion, ACR)
- Use NSGs to restrict traffic per subnet

---

## 3. VNet Peering

- Connect VNets within same region or across regions
- Peering is private and low-latency
- No need for VPN or public IPs

```bash
az network vnet peering create --name peer1   --resource-group RG   --vnet-name VNet1 --remote-vnet VNet2   --allow-vnet-access
```

---

## 4. DNS Options

- Default: Azure-provided internal DNS
- Custom DNS servers: forward to on-prem
- Use Azure Private DNS Zones for resolution inside VNets

---

## 5. Security Features

- NSG: Layer-4 filtering per subnet or NIC
- ASG: Group IPs dynamically by tags (e.g., Web servers)
- Route Tables: Define custom UDR for next hop

---

## 6. Design Patterns

- Hub and Spoke: Shared services in hub, spoke VNets per app
- Mesh: Peering all VNets (only for small networks)

---

## 7. Best Practices

- Use NSG + ASG combination for scalability
- Enable flow logs to NSG for monitoring
- Document VNet topology with address space/subnet list
