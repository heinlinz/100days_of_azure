# 100 Days of Azure – Day 03  

## Azure CLI – Virtual Machine Creation

## Overview  

This task focuses on using the Azure CLI to create a Virtual Machine from the command line.

---

## What I Did  

- Listed resource groups  
- Created a Linux Virtual Machine using Azure CLI  
- Configured SSH access and storage  

---

## Commands Used  

```bash
az group list -o table

az vm create \
  --resource-group kml_rg_main-ef1b3157438c45e5 \
  --name datacenter-vm \
  --image Ubuntu2204 \
  --size Standard_B2s \
  --admin-username azureuser \
  --generate-ssh-keys \
  --storage-sku Standard_LRS \
  --os-disk-size-gb 30
