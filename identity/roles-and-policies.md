
# Azure Roles, RBAC, and Conditional Access Policies

Proper access and security policy design is critical to a secure Azure environment.

---

## 1. Azure RBAC

Role-Based Access Control (RBAC) assigns permissions to users, groups, or applications at specific scopes.

| Scope        | Examples                |
|--------------|-------------------------|
| Management Group | Apply policy across subscriptions |
| Subscription | Control billing, resource visibility |
| Resource Group | Isolate workload teams |
| Resource     | Specific VM, Storage, etc. |

---

## 2. Built-in Roles

- **Owner**: Full access including access management
- **Contributor**: Full except access control
- **Reader**: View-only
- **User Access Administrator**: Manage access

---

## 3. Custom Roles

Define with JSON:
```json
{
  "Name": "VM Operator",
  "Actions": [
    "Microsoft.Compute/virtualMachines/start/action",
    "Microsoft.Compute/virtualMachines/read"
  ],
  "AssignableScopes": ["/subscriptions/xxxxxxxx"]
}
```

---

## 4. Conditional Access Policies

Define real-time access conditions:

- **Conditions**: User group, location, device state
- **Controls**: MFA, require compliant device, block

Example:
- Require MFA for users outside of trusted IPs
- Block legacy authentication protocols

---

## 5. Recommendations

- Use groups instead of individuals in assignments
- Apply least privilege
- Regularly audit assignments
- Use PIM for elevated role management
