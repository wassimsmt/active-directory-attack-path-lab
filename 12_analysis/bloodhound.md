\# BloodHound Analysis



\## Tooling

\- SharpHound (data collection from WS01)

\- BloodHound (Neo4j backend)



\## Data Collection

BloodHound data was collected from a domain-joined workstation using valid user credentials and transferred to the analysis system for offline review.



Collected datasets included:

\- Users

\- Groups

\- Computers

\- Domain objects

\- ACLs and delegation relationships



\## Methodology

The following methodology was used:

1\. Import SharpHound data into BloodHound

2\. Mark compromised users as "Owned"

3\. Perform pathfinding queries to Domain Admins

4\. Analyze edge types and permission relationships



\## Key Findings

\- HELPDESK user displayed a valid path to Domain Admins

\- Path relied on delegated permissions rather than direct group membership

\- Multiple high-risk edge types were observed (e.g., GenericWrite, delegation-related permissions)



\## Observations

\- Role names did not accurately reflect privilege level

\- Delegation configurations significantly expanded attack surface

\- BloodHound provided visibility not achievable through traditional enumeration alone



\## Value of BloodHound

This phase demonstrated how privilege escalation often results from cumulative misconfigurations rather than a single critical flaw.



