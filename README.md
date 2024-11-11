# Terraform Azure Backend setup

This project creats Azure storage accounts for storing backend

# Create a service principle to manage resources in specified Subscription

Ref: [https://learn.microsoft.com/en-us/azure/developer/terraform/store-state-in-azure-storage?tabs=azure-cli](Store Terraform state in Azure Storage)

```bash
az ad sp create-for-rbac --role="Contribtor" --scopes="/subscriptions/20000000-0000-0000-0000-000000000000"
```

## These values map to the Terraform variables like so:

- appId is the `client_id` defined above.
- password is the `client_secret` defined above.
- tenant is the `tenant_id` defined above.

example:

```json
{
  "appId": "9cd********-****-*****-*******",
  "displayName": "azure-cli-2024-11-10-14-57-19",
  "password": "**********",
  "tenant": "11f1********-****-*****-*******"
}
```


## Resource Group

Create a [resource group using TF](terraform/az-backend/main.tf#8)


## Create Storage Account

Create a [storage account using TF](terraform/az-backend/main.tf#13)


## Deployment Proection Rules

TODO