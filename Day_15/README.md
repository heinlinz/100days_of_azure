# 100 Days of Azure – Day 15  
## Create and Configure Azure Network Security Group (NSG)

## Overview  
This task demonstrates how to create an Azure Network Security Group (NSG) and configure inbound security rules for HTTP and SSH access.

---

## What I Did  
- Created a new Network Security Group  
- Configured NSG basic settings  
- Added an inbound HTTP rule for port 80  
- Added an inbound SSH rule for port 22  
- Configured priorities for both rules  
- Verified both security rules were successfully added  

---

## Configuration Used  

| Setting | Value |
|---|---|
| NSG Name | `devops-nsg` |
| Region | East US |
| HTTP Port | `80` |
| SSH Port | `22` |
| HTTP Priority | `100` |
| SSH Priority | `110` |
| Protocol | TCP |
| Source | `0.0.0.0/0` |

---

## Steps Performed  

### 1. Open Network Security Groups and Click Create  
![Create NSG](./screenshots/create_nsg.png)

---

### 2. Configure NSG Basic Settings  
- Entered NSG name: `devops-nsg`
- Selected region: `East US`
- Selected resource group

![Configure NSG](./screenshots/configure.png)

---

### 3. Review and Create the NSG  
- Left remaining settings as default
- Clicked **Create**

![Review and Create](./screenshots/the_rest_to_default_and_create.png)

---

### 4. Open Inbound Security Rules and Click Add  
![Go to Inbound Rules](./screenshots/go_to_inbound_and_click_add.png)

---

## Configure HTTP Rule

### 5. Configure HTTP Inbound Rule  
- Source: `0.0.0.0/0`
- Destination Port: `80`
- Protocol: `TCP`
- Action: `Allow`

![HTTP Settings](./screenshots/configure_http_settings.png)

---

### 6. Set Rule Name and Priority  
- Priority: `100`
- Rule Name: `Allow-HTTP`

![Name HTTP Rule](./screenshots/name_and_click_add.png)

---

### 7. Verify HTTP Rule Added  
![HTTP Rule Added](./screenshots/make_sure_added_and_click_add_again.png)

---

## Configure SSH Rule

### 8. Configure SSH Inbound Rule  
- Service: `SSH`
- Port: `22`
- Protocol: `TCP`
- Action: `Allow`

![SSH Settings](./screenshots/configure_ssh_settings.png)

---

### 9. Set SSH Rule Name and Priority  
- Priority: `110`
- Rule Name: `Allow-SSH`

![Name SSH Rule](./screenshots/name_and_add.png)

---

### 10. Verify Both Rules Were Added  
![Final Rules](./screenshots/make_sure_two_nsgs.png)

---

## Result  
Successfully created an Azure Network Security Group named:

```text
devops-nsg
