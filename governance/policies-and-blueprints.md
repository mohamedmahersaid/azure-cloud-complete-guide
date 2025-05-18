
# Azure Policy and Blueprint Governance

Use Azure Policy to enforce rules and effects across your Azure environment.

---

## 1. Policy Definitions

- Built-in or custom
- Examples:
  - Allowed locations
  - Enforce tags
  - VM SKU restrictions

---

## 2. Initiative = Group of Policies

- Assign multiple policies as one package
- Scope to MGs, subscriptions, or RGs

---

## 3. Blueprint (deprecated → use Template Specs)

- Combine ARM templates + Policy + RBAC in one deployable package
