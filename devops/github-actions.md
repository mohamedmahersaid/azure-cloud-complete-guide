
# CI/CD with GitHub Actions for Azure

GitHub Actions integrates directly with Azure for IaC, app deployment, and testing.

---

## 1. Workflow Example

```yaml
name: Deploy Bicep to Azure

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Login to Azure
      uses: azure/login@v1
      with:
        creds: ${{ secrets.AZURE_CREDENTIALS }}

    - name: Deploy Bicep
      run: |
        az deployment group create --resource-group demo-rg --template-file main.bicep
```
