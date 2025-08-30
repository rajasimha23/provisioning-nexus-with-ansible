# Nexus Deployment with Ansible

This project contains an **Ansible playbook** and a **shell script** to automate the deployment of Sonatype Nexus Repository.

---

## Files
├── deploy-nexus.yaml # Ansible playbook for Nexus deployment
├── nexus.sh # Raw shell commands for manual setup
├── project.vars # Variables file (optional for customization)
├── hosts # Ansible inventory file

---

## Prerequisites
- Linux host (tested on Ubuntu/Debian)  
- [Ansible](https://docs.ansible.com/) ≥ 2.9  
- Python ≥ 3.x  
- SSH access and sudo privileges  

---

## Usage

### 1. Configure Inventory
Edit the `hosts` file:
```ini
[nexus_server]
192.168.1.10 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa

### 2. Run the Playbook
ansible-playbook -i hosts deploy-nexus.yaml


This will:

- Install Java and net-tools

- Download and extract Nexus

- Create a nexus user and set permissions

- Configure Nexus to run as the nexus user

- Start Nexus and verify it is running

### 3. Manual Deployment (Optional)

Run:
```
./nexus.sh


This script contains the equivalent raw commands for manual Nexus installation.