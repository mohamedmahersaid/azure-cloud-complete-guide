
# Azure Key Vault and Secrets Management

Azure Key Vault stores secrets, keys, and certificates securely in the cloud.

---

## 1. Use Cases

- Store connection strings and app secrets
- Encrypt disks and blobs with customer-managed keys (CMK)
- TLS/SSL certificate management

---

## 2. Vault Types

| Type       | Description              |
|------------|--------------------------|
| Standard   | Public and private endpoints |
| Premium    | Supports HSM-protected keys |

---

## 3. Access Control

- RBAC (recommended): Assign roles like `Key Vault Secrets User`
- Access Policies: Legacy but still supported
- Use Private Endpoint to lock down access

---

## 4. Secure Access via Managed Identity

Grant access to VM/app using system-assigned identity:

```bicep
resource kv 'Microsoft.KeyVault/vaults@2022-07-01' = {
  name: 'myVault'
  location: resourceGroup().location
  properties: {
    ...
    accessPolicies: []
  }
}

output kvUri string = kv.properties.vaultUri
```

---

## 5. Integration Examples

- App Service: bind to secrets via environment variables
- Function App: use Key Vault reference in `local.settings.json`
- Disk Encryption: Use Key Vault for customer-managed encryption keys

---

## 6. Monitoring

- Enable diagnostic settings → Log Analytics
- Track `SecretGet`, `SecretSet`, `KeyEncrypt` operations

---

## 7. Best Practices

- Disallow public access unless required
- Use soft-delete and purge protection
- Rotate secrets and keys on a schedule
