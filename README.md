# 🛡️ Active Directory Attack Path Analysis Lab

## 🧭 Lab Architecture

```
          Internal Active Directory Environment (corp.local)

+----------------+        Internal Network         +----------------------+
|   Kali Linux   | <-----------------------------> |  Domain Controller   |
|   (Attacker)   |                                 |      (DC01)          |
|                |                                 | - Active Directory   |
| - Nmap         |                                 | - LDAP / Kerberos    |
| - SMB Enum     |                                 | - DNS Services       |
| - LDAP Queries |                                 +----------------------+
| - Kerbrute     |                                          |
| - BloodHound   |                                           |
+----------------+                                            |
                                                               |
                                                      +------------------+
                                                      |   Workstation    |
                                                      |      (WS01)      |
                                                      | - Domain Joined  |
                                                      | - User Sessions  |
                                                      +------------------+
```

Assessment Flow:
Discovery → Service Enumeration → Credential Testing → BloodHound Analysis → Attack Path Identification

## 🔎 Project Overview
This project simulates a **realistic internal Active Directory penetration test** conducted in a fully isolated lab environment.  
The objective was not to “hack for the sake of hacking”, but to **understand, analyze, and document how misconfigurations inside Active Directory can lead to critical privilege escalation**.

The project took place over several days and involved designing the lab, troubleshooting networking and domain issues, performing enumeration, analyzing privilege relationships, and documenting realistic attack paths.

---

## 🎯 Goals of the Project
- Build a functional Active Directory lab from scratch
- Perform internal enumeration as a low-privileged domain user
- Analyze domain relationships and delegated permissions
- Identify realistic privilege escalation paths
- Document findings in a professional and structured way
- Focus on **reasoning and analysis**, not reckless exploitation

---

## 🧪 Lab Environment
The lab was built using VirtualBox and consists of:

- 🖥️ **Domain Controller (DC01)**  
  Windows Server acting as the Active Directory Domain Controller

- 💻 **Workstation (WS01)**  
  Domain-joined Windows client machine

- 🐧 **Attacker Machine (Kali Linux)**  
  Used for enumeration, analysis, and data collection

- 🌐 **Domain:** `corp.local`  
- 🔒 **Network:** Isolated host-only + NAT setup (no external exposure)

---

## 🧭 Methodology
The assessment followed a structured internal penetration testing workflow:

### 1️⃣ Network Discovery
- Host discovery inside the internal network
- Identification of domain systems and exposed services

### 2️⃣ Service Enumeration
- SMB enumeration (shares, signing, OS information)
- LDAP enumeration (RootDSE, domain users)
- Kerberos enumeration (user validation and AS-REP roasting checks)

### 3️⃣ Credential Testing (Lab-Safe)
- Password spraying using known weak credentials
- Focused on validation, not brute force

### 4️⃣ Active Directory Relationship Analysis
- BloodHound data collection
- Graph-based analysis of:
  - User privileges
  - Group memberships
  - Delegated permissions
  - Attack paths to high-value targets

---

## 🔑 Key Findings
- Active Directory domain services were accessible internally
- Weak password hygiene existed on multiple accounts
- Delegated permissions were misconfigured
- Most low-privileged users had **no escalation path**
- A **Helpdesk account had a valid attack path to Domain Admin**
- Privilege escalation risk was caused by **design and configuration flaws**, not software vulnerabilities

---

## 🚨 Impact Analysis
If the Helpdesk account were compromised in a real organization, an attacker could:
- Escalate privileges to Domain Admin
- Gain full control over Active Directory
- Access credentials across the domain
- Move laterally to all domain-joined systems
- Completely compromise trust within the environment

This highlights how **internal misconfigurations can be more dangerous than external exploits**.

---

## 🛠️ Tools Used
- Nmap
- smbclient
- ldapsearch
- kerbrute
- BloodHound / SharpHound
- Native Windows Active Directory tools

---

## 📂 Repository Structure
The repository is organized to reflect a professional assessment:

- `02_discovery/` – Network discovery results  
- `03_service_enum/` – Service enumeration outputs  
- `04_smb/` – SMB enumeration findings  
- `05_kerberos/` – Kerberos-related enumeration  
- `06_ldap/` – LDAP queries and results  
- `07_passwords/` – Password spray results (lab-safe)  
- `08_bloodhound/` – BloodHound data and analysis  
- `screenshots/` – Evidence and analysis screenshots  
- `scope.md` – Scope definition  
- `attack_path_explanation.md` – Attack path reasoning  
- `bloodhound.md` – Graph analysis details  
- `impact.md` – Business and security impact  
- `personal_notes.md` – Reflections and learning notes  

---

## ⚠️ Disclaimer
All activities were conducted **strictly in a personal lab environment** created for educational purposes.  
No real-world systems were accessed or targeted.

---

## 📈 What This Project Demonstrates
- Understanding of Active Directory internals
- Ability to reason about privilege escalation without relying on exploits
- Experience with real-world enumeration techniques
- Professional documentation and reporting mindset
- Growth from tool usage to **security analysis**

---

## 👤 Author
**Wassim Abelghouch**  
Cybersecurity Student | Aspiring Penetration Tester


