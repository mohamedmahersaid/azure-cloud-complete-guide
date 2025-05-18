
# Azure ExpressRoute and VPN Gateway Integration

For hybrid scenarios, Azure supports both ExpressRoute (private fiber) and VPN (IPSec tunnels).

---

## 1. ExpressRoute

- Private, dedicated link to Azure
- Not over public internet
- Supports Microsoft Peering, Private Peering, and Internet Peering

### Use Cases

- High bandwidth (up to 100 Gbps)
- SLA-backed enterprise workloads
- Direct access to PaaS services via Microsoft peering

---

## 2. VPN Gateway

- Encrypted IPSec tunnels over public internet
- Use Site-to-Site (S2S) or Point-to-Site (P2S)
- Ideal for small/medium workloads or redundancy

---

## 3. Coexistence Model

Use ExpressRoute as primary and VPN as failover (BGP routing preferred).

---

## 4. Comparison

| Feature          | ExpressRoute   | VPN Gateway     |
|------------------|----------------|-----------------|
| Latency          | Low            | Medium          |
| Bandwidth        | Up to 100 Gbps | Up to 1.25 Gbps |
| SLA              | Yes            | Yes             |
| Encryption       | Optional       | IPSec           |
| Cost             | High           | Lower           |

---

## 5. Monitoring and Management

- Use Network Watcher for packet capture and connection troubleshooting
- Enable logs for Gateway diagnostics and ExpressRoute circuits

---

## 6. References

- [ExpressRoute documentation](https://learn.microsoft.com/en-us/azure/expressroute/)
- [VPN Gateway documentation](https://learn.microsoft.com/en-us/azure/vpn-gateway/)
