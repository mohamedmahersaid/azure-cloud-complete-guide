
# Hybrid Identity with Azure AD Connect

Azure AD Connect synchronizes on-premises AD with Azure AD for hybrid identity management.

---

## 1. Key Features

- Password hash sync or pass-through auth
- Writeback for passwords, groups
- Seamless SSO support

---

## 2. Sync Modes

| Mode            | Description |
|-----------------|-------------|
| Password Hash   | Default, simple, secure |
| PTA             | On-prem validation |
| Federation      | Requires ADFS setup |

---

## 3. Best Practices

- Monitor sync health via Azure AD Connect Health
- Staging server for redundancy
- Filter OUs and attributes
