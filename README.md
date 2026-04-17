
# Linux User Group & File Permission Management

## 📌 Overview

This project demonstrates fundamental Linux system administration tasks, including:

- Creation and management of users and groups
- Assignment of secondary group memberships
- Setting directory-level permissions using both symbolic and numeric methods
- Verification of access rights through practical testing

The scenario simulates an organizational environment with two departments: **HR** and **IT**. Two users (`amina` and `kola`) are created and assigned to respective departments, with controlled access to shared directories.

---

## 🛠️ Environment

- **OS**: Kali Linux  
- **Shell**: Bash  
- **Privileges**: `sudo` access for administrative commands  

---

## 📁 Steps Performed

### 1. Group Creation

sudo groupadd HR

sudo groupadd IT

---
## 2. User Creation & Password Setup
sudo useradd amina

sudo useradd kola

sudo passwd amina

sudo passwd kola

---

## 3. Assign Users to Groups
sudo usermod -aG HR amina

sudo usermod -aG IT kola

---
### Verification:
id amina
### uid=1001(amina) gid=1003(amina) groups=1003(amina),1001(HR)


id kola
### uid=1002(kola) gid=1004(kola) groups=1004(kola),1002(IT)

---

## 4. Create Shared Directories & Set Permissions
sudo mkdir -p /shared/hr_docs /shared/it_docs

sudo chmod 770 /shared/hr_docs

sudo chmod 770 /shared/it_docs

---

## 5. Create Test Files
sudo touch /shared/hr_docs/hr_file.txt

sudo touch /shared/it_docs/it_file.txt

---

### Ownership & Permission Check:
ls -ld /shared/*
### drwxrwx--- 2 root HR 4096 Apr 16 03:32 /shared/hr_docs

### drwxrwx--- 2 root IT 4096 Apr 16 03:32 /shared/it_docs

---

## 6. Testing & Modifying Group Membership
### User amina was temporarily added to the IT group and then removed to test access changes.

sudo usermod -aG IT amina   # add

sudo gpasswd -d amina IT    # remove



