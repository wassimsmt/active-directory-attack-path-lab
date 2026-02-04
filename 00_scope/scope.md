\# Scope Definition



\## Engagement Type

Internal Network Penetration Test – Active Directory Environment (Lab)



\## Objective

The objective of this engagement was to identify and validate security weaknesses within an internal Active Directory (AD) environment that could allow a low-privileged domain user to escalate privileges or compromise critical domain assets.



This project was conducted in a controlled lab environment owned and operated by the author for educational and portfolio purposes.



\## In-Scope Assets

The following systems and services were included in scope:



\- Active Directory Domain: corp.local

\- Domain Controller: DC01.corp.local

\- Domain-Joined Workstation: WS01.corp.local

\- Internal network services exposed by the domain controller and workstation (LDAP, Kerberos, SMB, DNS, RPC)



\## Out-of-Scope

\- Denial-of-Service attacks

\- Attacks against external networks

\- Exploitation of vulnerabilities requiring unpatched zero-day exploits

\- Persistence beyond proof-of-concept validation



\## Assumptions

\- The tester begins with internal network access

\- No prior administrative credentials are assumed

\- All findings are validated through evidence-based enumeration and analysis



\## Rules of Engagement

\- No destructive actions were performed

\- Changes made during the lab were limited to configuration required for validation

\- All attack paths were documented and reversible



