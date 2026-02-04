\# Attack Path Explanation



\## Overview

This assessment identified a viable privilege escalation path originating from a delegated support account within the domain. While not all compromised users led directly to Domain Administrator privileges, at least one user (HELPDESK) demonstrated a valid attack path when analyzed using BloodHound.



\## Initial Access Context

The attacker is assumed to have access equivalent to a low-privileged authenticated domain user. No administrative privileges were assumed at the start of the engagement.



\## Identified Privileged User Relationships

Through authenticated enumeration and BloodHound analysis, the following user accounts were marked as controlled or owned:



\- JDON

\- HELPDESK

\- BACKUP.ADMIN



Only the HELPDESK account demonstrated a valid path to higher privilege.



\## BloodHound Findings

BloodHound revealed that:



\- HELPDESK is a member of a delegated support group

\- The delegated group possesses extended rights over domain objects

\- The delegation chain allows indirect influence over privileged accounts or systems

\- A valid path to Domain Admin–level control exists through misconfigured permissions



\## Non-Exploitable Paths

\- JDON: No path found to Domain Admin

\- BACKUP.ADMIN: No direct or indirect path found despite elevated-sounding role



This demonstrates the importance of permission-based analysis over role naming conventions.



\## Conclusion

The attack path identified is not the result of a single vulnerability, but rather a combination of:

\- Over-delegation

\- Excessive group permissions

\- Lack of tiered administrative separation



These issues collectively enable privilege escalation in a real-world scenario.



