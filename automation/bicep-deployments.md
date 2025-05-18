
# Infrastructure as Code with Bicep

Bicep is a domain-specific language (DSL) that simplifies the authoring of ARM templates for Azure.

---

## 1. Getting Started

- Install Bicep CLI:
```bash
az bicep install
```

- Validate Bicep files:
```bash
az bicep build --file main.bicep
```

---

## 2. Sample Bicep: Create Resource Group and Storage Account

```bicep
param location string = resourceGroup().location
param storageName string

resource sa 'Microsoft.Storage/storageAccounts@2022-09-01' = {
  name: storageName
  location: location
  sku: {
    name: 'Standard_LRS'
  }
  kind: 'StorageV2'
  properties: {}
}
```

Deploy it:
```bash
az deployment group create -g MyResourceGroup -f main.bicep --parameters storageName=mystorage123
```

---

## 3. Best Practices

- Use modules for reusable components
- Use parameter files for environments
- Store in Git with version control

---

## 4. Tools

- VS Code Bicep extension
- Azure Resource Visualizer
