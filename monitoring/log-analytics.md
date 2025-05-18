
# Log Analytics and Azure Monitor Overview

Azure Monitor and Log Analytics provide centralized observability across all Azure resources.

---

## 1. Log Analytics Workspace

- Centralized log store for metrics and telemetry
- Query using KQL (Kusto Query Language)
- Connected services: VM insights, Defender for Cloud, Activity Logs

---

## 2. Enable Diagnostic Settings

- Required to send platform logs to:
  - Log Analytics
  - Storage Account
  - Event Hub

```bash
az monitor diagnostic-settings create --name diagSettings   --resource <resource-id>   --workspace <log-analytics-id>   --logs '[{"category":"AllLogs","enabled":true}]'
```

---

## 3. Sample KQL Queries

### Get VM CPU over time
```kql
Perf
| where ObjectName == "Processor" and CounterName == "% Processor Time"
| summarize avg(CounterValue) by bin(TimeGenerated, 5m), Computer
```

### Get audit events from Key Vault
```kql
AzureDiagnostics
| where ResourceType == "VAULTS" and OperationName contains "Secret"
```

---

## 4. Workbooks and Dashboards

- Visualize metrics and logs using built-in or custom workbooks
- Pin results to Azure Dashboard

---

## 5. Best Practices

- Use one workspace per region/business unit
- Set data retention based on compliance
- Group related queries in saved Workbooks
