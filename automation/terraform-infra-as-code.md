
# Infrastructure as Code with Terraform

Terraform is a popular open-source IaC tool that supports Azure natively via the `azurerm` provider.

---

## 1. Setup

- Install Terraform CLI: https://www.terraform.io/downloads
- Configure backend (Azure Storage for remote state)
- Authenticate via Azure CLI or Service Principal

---

## 2. Basic Terraform Structure

```hcl
provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "rg" {
  name     = "example-rg"
  location = "East US"
}

resource "azurerm_storage_account" "sa" {
  name                     = "examplestoracc"
  resource_group_name      = azurerm_resource_group.rg.name
  location                 = azurerm_resource_group.rg.location
  account_tier             = "Standard"
  account_replication_type = "LRS"
}
```

---

## 3. Deployment Steps

```bash
terraform init
terraform plan
terraform apply
```

---

## 4. Best Practices

- Use modules for common components
- Store state remotely with locking
- Use `terraform-docs` for documentation

---

## 5. CI/CD Integration

- Azure DevOps pipelines
- GitHub Actions with Terraform workflow
