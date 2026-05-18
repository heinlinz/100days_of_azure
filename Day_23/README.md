# 100 Days of Azure – Day 23  
## Creating an Azure VM with NGINX Using Custom Data

## Overview  
This lab creates an Azure Virtual Machine using Azure CLI and installs NGINX automatically with a custom script.

---

## What I Did  
- Created a Bash script to install NGINX
- Created an Azure VM using Azure CLI
- Passed the script using custom data
- Opened port 80 for HTTP access
- Checked VM and NSG details

---

## Steps Performed  

### 1. Create NGINX Script  

```bash
vi nginx.sh
```

Added the script:

```bash
#!/bin/bash
apt update -y
apt install -y nginx
systemctl start nginx
systemctl enable nginx
```

Saved and exited the file.

---

### 2. List Resource Groups  

```bash
az group list -o table
```

Copied the required resource group name.

---

### 3. Create Virtual Machine  

```bash
az vm create \
  --resource-group <resource-group-name> \
  --name <vm-name> \
  --image Ubuntu2404 \
  --location eastus \
  --size Standard_B1s \
  --admin-username azureuser \
  --generate-ssh-keys \
  --custom-data nginx.sh \
  --os-disk-size-gb 30 \
  --storage-sku Standard_LRS
```

---

### 4. Get Network Security Group Name  

```bash
az resource list \
  --resource-group <resource-group-name> \
  -o table
```

Used the output to find the NSG name.

---

### 5. Open HTTP Port 80  

```bash
az vm open-port \
  --resource-group <resource-group-name> \
  --name <vm-name> \
  --port 80
```

---

### 6. List NSG Rules  

```bash
az network nsg rule list \
  --resource-group <resource-group-name> \
  --nsg-name <nsg-name> \
  -o table
```

---

### 7. Show VM Details  

```bash
az vm show \
  --resource-group <resource-group-name> \
  --name <vm-name> \
  --show-details \
  -o table
```

---

## Author  
Hein Lin Zaw
