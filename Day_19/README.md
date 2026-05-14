# 100 Days of Azure – Day 19  
## Changing Azure Blob Container Access Level

## Overview  
This lab demonstrates how to manage access levels for Azure Blob Containers.  
The task involved changing a public container back to private access using the Azure Portal.

---

## What I Did  
- Navigated to Azure Storage Account Containers  
- Selected a public blob container  
- Opened the access level settings  
- Changed anonymous access from public to private  
- Verified the container access level was updated successfully  

---

## Steps Performed  

### 1. Open Storage Account Containers  

Navigated to the Azure Storage Account and opened the **Containers** section.

![Open Containers](./screenshots/go_to_storage_accounts_container.png)

---

### 2. Select Public Container  

Selected the public container and clicked:

```text
Change access level
```

![Select Container](./screenshots/select_pub_container_and_click_change_access.png)

---

### 3. Change Access Level to Private  

Changed the anonymous access level to:

```text
Private (no anonymous access)
```

Then clicked:

```text
Ok
```

![Choose Private Access](./screenshots/choose_prvate_and_hit_ok.png)

---

### 4. Verify Container is Private  

Verified that the container access level changed successfully from:

```text
Container
```

to:

```text
Private
```

![Verify Private Access](./screenshots/make_sure_private.png)

---

## Result  

Successfully:
- Accessed Azure Blob Container settings
- Modified anonymous access permissions
- Changed a public container into a private container
- Verified secure private access configuration

---

## Author  
Hein Lin Zaw
