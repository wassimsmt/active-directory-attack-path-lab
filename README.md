\# Internal Network Penetration Test – Active Directory



\## Overview

This repository documents an internal Active Directory penetration test conducted in a controlled lab environment. The project follows a structured, OSCP-style methodology from discovery to attack path analysis.



The focus of this engagement is \*\*privilege escalation through Active Directory misconfigurations\*\*, not exploitation of software vulnerabilities.



\## Environment

\- Domain: corp.local

\- Domain Controller: DC01

\- Workstation: WS01

\- Attacker System: Kali Linux



\## Methodology

1\. Scope definition

2\. Network and service discovery

3\. Domain enumeration (SMB, LDAP, Kerberos)

4\. Authenticated enumeration

5\. BloodHound attack path analysis

6\. Impact assessment and documentation



\## Key Findings

\- Over-delegation of permissions enabled privilege escalation

\- One support account (HELPDESK) had a valid path to Domain Admin

\- Other users with elevated-sounding roles did not present exploitable paths

\- Risk originated from ACL and delegation misconfiguration



\## Tools Used

\- Nmap

\- Kerbrute

\- LDAP utilities

\- SMB clients

\- SharpHound / BloodHound

\- Neo4j



\## Disclaimer

This project was conducted in a personal lab environment for educational and portfolio purposes only. No unauthorized systems were targeted.



\## Author

Wassim Abelghouch

Internal Network \& Active Directory Security Practice



