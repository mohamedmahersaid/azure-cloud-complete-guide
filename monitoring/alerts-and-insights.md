
# Azure Alerts and Insights

Proactive alerting and workload insights help detect and remediate issues early.

---

## 1. Alert Types

| Type         | Purpose                     |
|--------------|-----------------------------|
| Metric Alerts| CPU, Memory, Disk thresholds|
| Log Alerts   | Based on KQL queries        |
| Activity Log | Detect resource changes     |
| Smart Alerts | Based on AI/ML              |

---

## 2. Create Alert Rule

1. Target resource (VM, SQL, etc.)
2. Define condition (CPU > 80% for 5 minutes)
3. Action Group:
   - Email, SMS, Push
   - Webhook, Logic App, ITSM connector

---

## 3. Action Groups

- Shared across subscriptions
- Use for incident automation or notification
- Tag action groups by environment/team

---

## 4. Insights

| Insight      | Description                        |
|--------------|------------------------------------|
| VM Insights  | CPU, disk, boot diagnostics        |
| Container Insights | AKS health and logs          |
| App Insights | Full-stack app monitoring          |
| Network Watcher | Packet flow and metrics         |

---

## 5. Best Practices

- Route alerts to centralized teams
- Suppress flapping alerts
- Use dynamic thresholds where possible
