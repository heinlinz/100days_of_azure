# 100 Days of Azure – Day 32

## Copying a Blob Between Storage Containers Using Azure CLI

## Overview

This lab demonstrates how to create a destination storage container, list existing containers and blobs, and copy a blob from a source container to a destination container using the Azure CLI.

---

## What I Did

- Created a new destination storage container using the Azure CLI
- Listed all containers in the storage account to verify creation
- Listed blobs in the source container to identify the file to copy
- Copied a blob from the source container to the destination container
- Verified the blob appeared in the destination container

---

## Steps Performed

### 1. Create the Destination Container

Created a new storage container to serve as the copy destination:

```bash
az storage container create \
  --name <destination-container-name> \
  --account-name <storage-account-name>
```

Example:

```bash
az storage container create \
  --name datacenter-dest-18874 \
  --account-name datacenterst26017
```

---

### 2. List All Containers

Verified the new container was created successfully by listing all containers in the storage account:

```bash
az storage container list \
  --account-name <storage-account-name> \
  -o table
```

Example:

```bash
az storage container list \
  --account-name datacenterst26017 \
  -o table
```

Both the source and destination containers should appear in the output.

---

### 3. List Blobs in the Source Container

Listed the blobs inside the source container to identify the file to be copied:

```bash
az storage blob list \
  -c <source-container-name> \
  --account-name <storage-account-name> \
  -o table
```

Example:

```bash
az storage blob list \
  -c datacenter-source-28397 \
  --account-name datacenterst26017 \
  -o table
```

Confirmed the target blob (e.g. `datacenter.txt`) was present in the source container.

---

### 4. Copy the Blob to the Destination Container

Copied the blob from the source container to the destination container:

```bash
az storage blob copy start \
  --account-name <storage-account-name> \
  --destination-container <destination-container-name> \
  --destination-blob <blob-name> \
  --source-container <source-container-name> \
  --source-blob <blob-name>
```

Example:

```bash
az storage blob copy start \
  --account-name datacenterst26017 \
  --destination-container datacenter-dest-18874 \
  --destination-blob datacenter.txt \
  --source-container datacenter-source-28397 \
  --source-blob datacenter.txt
```

Azure initiated the copy operation asynchronously.

---

### 5. Verify the Blob in the Destination Container

Listed the blobs in the destination container to confirm the copy was successful:

```bash
az storage blob list \
  -c <destination-container-name> \
  --account-name <storage-account-name> \
  -o table
```

Example:

```bash
az storage blob list \
  -c datacenter-dest-18874 \
  --account-name datacenterst26017 \
  -o table
```

The copied blob should now appear in the destination container output.

---

## Author

Hein Lin Zaw
