
# Azure Active Directory (Azure AD) Architecture

Azure AD is Microsoft’s cloud-based identity and access management service, the foundation of secure Azure workloads.

---

## 1. Core Components

| Component            | Description |
|----------------------|-------------|
| Tenants              | Dedicated, isolated instance of Azure AD |
| Directory            | Logical container of users, groups, devices |
| Azure AD Connect     | Sync on-prem AD to Azure AD |
| Identities           | Users, groups, service principals |
| External Identities  | B2B collaboration with guests |
| Authentication       | MFA, SSPR, Conditional Access |

---

## 2. Identity Types

- **Cloud-only**: created directly in Azure AD
- **Synchronized**: via Azure AD Connect (hybrid)
- **Federated**: Auth via ADFS or third-party IdP

---

## 3. Authentication Flows

- **Password Hash Sync (PHS)** – default, secure
- **Pass-Through Auth (PTA)** – validates via local agent
- **Federation** – ADFS or external identity provider

---

## 4. Identity Protection

- Risk-based Conditional Access
- Sign-in risk & user risk policies
- MFA enforcement (Microsoft Authenticator, SMS, FIDO2)

---

## 5. Access Management

- Azure AD RBAC (roles assigned at Azure resource level)
- Admin Roles (Global Admin, User Admin, Security Admin)
- PIM (Privileged Identity Management) for JIT access

---

## 6. Directory Design Tips

- One tenant for most orgs
- Use nested groups with caution
- Enforce naming standards for users and groups

---

## 7. Monitoring & Logs

- Sign-in logs via Azure AD
- Audit logs (user/group changes)
- Integrate with Log Analytics

---

## 8. References

- [Azure AD Overview](https://learn.microsoft.com/en-us/azure/active-directory/fundamentals/)
