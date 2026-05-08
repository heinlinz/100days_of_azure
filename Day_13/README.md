# 100 Days of Azure – Day 13  

## Configure Root SSH Access Using Public Key Authentication

## Overview  

This project demonstrates how to configure SSH key-based authentication for the root user on an Azure Virtual Machine.

The process includes:

- Viewing the local public SSH key
- Connecting to the Azure VM
- Switching to the root user
- Adding the SSH public key to the root user's `authorized_keys`
- Logging in directly as the root user using SSH keys

---

# Step-by-Step Process

## Step 1 - Navigate to the Local SSH Directory and copy the public key

cd ~/.ssh/
cat id_rsa.pub

## Step 2 - SSH login to your vm with vm_ip(you can get it from dashboard)

ssh azureuser@<your_vm_ip>

## Step 3 - Switch to root user

sudo su

## Step 4 - Navigate to the root SSH Directory

cd /root/.ssh/

## Step 5 - Check if there's an authorized_keys file

ls

## Step 6 - Edit the authorized_keys file and paste the pub key

vi authorized_keys

## Step 7 - Logout and move to client vm_ip

exit

## Login with the root user

ssh root@<your_vm_ip>
