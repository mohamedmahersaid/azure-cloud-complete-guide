
# Azure Management Groups

Management Groups allow you to organize subscriptions for governance and policy enforcement.

---

## 1. Structure Example

```
Tenant Root
├── Corp
│   ├── Prod
│   └── Dev
├── Shared
└── Sandbox
```

---

## 2. Capabilities

- Scope RBAC roles
- Apply Azure Policies and Budgets
- Nest groups for logical inheritance
