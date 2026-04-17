
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
```bash
sudo groupadd HR
sudo groupadd IT
