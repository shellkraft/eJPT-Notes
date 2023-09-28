### Penetration Testing with Metasploit 

+ The MSF can be used to perform and automate various tasks that fall under the penetration testing life cycle. 

+ In order to understand how we can leverage the MSF for penetration testing, we need to explore the various phases of a penetration test and their respective techniques and objectives.

+ We can adopt the PTES (Penetration Testing Execution Standard) as a roadmap to understanding the various phases that make up a penetration test and how Metasploit can be integrated in to each phase.

### Penetration Testing Execution Standard

The Penetration Testing Execution Standard (PTES) is a penetration testing
methodology that was developed by a team of information security
practitioners with the aim of addressing the need for a comprehensive and
up-to-date standard for penetration testing.

### Penetration Testing Phases

1. Information Gathering

2. Enumeration

3. Exploitation

4. Post Exploitation
	+ Privilege Escalation 
	+ Maintaining Persistent Access
	+ Clearing Tracks

### `MSF` for Penetration Testing

| Penetration Testing Phase | MSF Implementation |
|-----------------|-----------------|
| Information Gathering & Enumeration   | Auxiliary Modules   |
| Vulnerability Scanning  | Auxiliary Modules, Nessus   |
| Exploitation   | Exploit Modules & Payloads   |
| Post Exploitation   | Meterpreter   |
| Privilege Escalation   | Post Exploitation Modules Meterpreter  |
| Maintaining Persistence   | Post Exploitation Modules Persistence   |

