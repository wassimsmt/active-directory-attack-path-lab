# 🛡️ Active Directory Attack Path Lab

## 🔍 Overview
This project simulates an **internal Active Directory penetration test** performed in a controlled lab environment. The goal is to identify misconfigurations, enumerate domain objects, and analyze realistic attack paths that could lead to high-impact compromise.

The focus is on **professional reasoning**, not reckless exploitation.

---

## 🧪 Lab Environment
- 🖥️ **Domain Controller:** Windows Server (DC01)
- 💻 **Workstation:** Windows Client (WS01)
- 🐧 **Attacker Machine:** Kali Linux
- 🌐 **Domain:** corp.local
- 🔒 **Network:** Isolated VirtualBox lab

---

## 🧭 Methodology
The assessment follows a real-world internal pentest workflow:

1️⃣ Network discovery & host identification  
2️⃣ Service enumeration (LDAP, SMB, Kerberos)  
3️⃣ Domain user & object enumeration  
4️⃣ Password spraying (lab-safe)  
5️⃣ BloodHound attack path analysis  
6️⃣ Risk & impact evaluation  

---

## 🚨 Key Findings
- Internal exposure of domain services
- Weak password hygiene on domain accounts
- Misconfigured delegated permissions
- Valid escalation path from **Helpdesk → Domain Admin**
- Other users confirmed with **no escalation path**

---

## 💥 Impact
Compromise of a Helpdesk account could result in:
- Full domain takeover
- Credential theft
- Lateral movement
- Total Active Directory trust failure

---

## 🛠️ Tools Used
- Nmap
- smbclient
- ldapsearch
- kerbrute
- BloodHound / SharpHound
- Active Directory administration tools

---

## ⚠️ Disclaimer
All activities were conducted **only in a personal lab environment** for educational purposes.

---

## 👤 Author
**Wassim Abelghouch**  
Cybersecurity Student | Aspiring Penetration Tester
