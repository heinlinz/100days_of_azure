# 100 Days of Azure – Day 20  

## Deploying a Virtual Network Using ARM Templates

## Overview  

This lab focused on deploying Azure infrastructure using an ARM (Azure Resource Manager) template.  
The task involved creating and configuring a JSON deployment template for an Azure Virtual Network and deploying it to a resource group using Azure CLI.

---

## What I Did  

- Navigated to the ARM templates directory  
- Edited a virtual network deployment template  
- Configured VNet properties inside the JSON file  
- Verified available Azure resource groups  
- Deployed the ARM template using Azure CLI  

---

## Commands Used  

### 1. Navigate to ARM Templates Directory  

```bash
ls /root/arm-templates
```

---

### 2. Edit ARM Deployment Template  

```bash
vi /root/arm-templates/vnet-deployment-template.json
```

---

### 3. Configure ARM Template  

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {},
    "functions": [],
    "variables": {},
    "resources": [
        {
            "name": "task-given-name",
            "type": "Microsoft.Network/virtualNetworks",
            "apiVersion": "2023-11-01",
            "location": "[resourceGroup().location]",
            "tags": {
                "displayName": "<task-given-name>",
                "Environment": "<env-value>"
            },
            "properties": {
                "addressSpace": {
                    "addressPrefixes": [
                        "<your-prefix>"
                    ]
                }
            }
        }
    ],
    "outputs": {
    }
}
```

---

### 4. Verify Resource Groups  

```bash
az group list --query '[].name' --output table | grep 'kml'
```

---

### 5. Deploy ARM Template  

```bash
az deployment group create \
  --resource-group <your-resource-group> \
  --template-file /root/arm-templates/vnet-deployment-template.json
```

---

## Author  

Hein Lin Zaw
