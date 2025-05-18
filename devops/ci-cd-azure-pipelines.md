
# CI/CD with Azure Pipelines

Azure DevOps Pipelines enable automated deployment and testing of infrastructure and apps.

---

## 1. YAML Example

```yaml
trigger:
  branches:
    include:
      - main

pool:
  vmImage: 'ubuntu-latest'

steps:
- checkout: self
- task: AzureCLI@2
  inputs:
    azureSubscription: 'ServiceConnection'
    scriptType: 'bash'
    scriptLocation: 'inlineScript'
    inlineScript: |
      az group create --name demo-rg --location eastus
```
