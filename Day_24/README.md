# 100 Days of Azure – Day 24  
## Creating and Accessing an Azure Linux Virtual Machine with SSH Keys

## Overview  
This lab demonstrates how to create an Azure Linux Virtual Machine using an existing SSH public key and connect to it securely using SSH.

---

## What I Did  
- Checked for existing SSH key pairs
- Generated SSH keys if not available
- Copied the public SSH key
- Created a new Azure Linux VM
- Configured VM storage and authentication
- Connected to the VM using SSH

---

## Steps Performed  

### 1. Check Existing SSH Keys  

```bash
ls .ssh/
```

Verified whether an SSH key pair already existed.

---

### 2. Generate SSH Key Pair (If Needed)  

If no SSH key existed:

```bash
ssh-keygen
```

---

### 3. Copy Public SSH Key  

```bash
cat .ssh/id_rsa.pub
```

Copied the public key for Azure VM authentication.

---

### 4. Open Virtual Machines Service  

Navigated to:

```text
Compute infrastructure → Virtual machines
```

Then clicked:

```text
Create → Virtual machine
```

![Create Virtual Machine](./screenshots/create_vm.png)

---

### 5. Configure VM Basics  

Configured:
- Resource group
- VM name
- Region
- Ubuntu 24.04 image

![Configure Basics](./screenshots/configure_name_and_region.png)

---

### 6. Configure Authentication  

Configured:
- SSH public key authentication
- Existing public SSH key
- SSH inbound access

![Use Existing SSH Public Key](./screenshots/use_existing_pub_key.png)

---

### 7. Configure Disk Settings  

Selected:

```text
Standard SSD
```

![Choose Standard SSD](./screenshots/choose_standard.png)

---

### 8. Review and Create VM  

Validated the configuration and created the virtual machine.

![Review and Create](./screenshots/review_and_create.png)

---

### 9. Copy Public IP Address  

After deployment, copied the VM public IP address.

![Copy Public IP](./screenshots/copy_public_ip.png)

---

### 10. Connect to the Virtual Machine  

```bash
ssh azureuser@<your_pub_ip>
```

---

## Author  
Hein Lin Zaw
