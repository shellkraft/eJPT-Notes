### History of Windows Vulnerabilities

- Microsoft Windows is the dominant operating system worldwide with a market share >=70% as of 2021

- The popularity and deployment of Windows by individuals and companies makes it a prime target for attackers given the threat surface.

- Over the last 15 years, Windows has had its fair share of severe vulnerabilities, ranging from MS08-067 (Conflicker) to MS17-010 (EternalBlue).

- Given the popularity of Windows, most of these vulnerabilities have publicly accessible exploit code making them relatively straightforward to exploit.

### Windows Vulnerabilities 

- Microsoft Windows has various OS versions and releases which makes the threat surface fragmented in terms of vulnerabilities. For example, vulnerabilities that exist in Windows 7 are not present in Windows 10. 3

- Regardless of the various versions and releases, all Windows OS'’s share a
likeness given the development model and philosophy:
	+ Windows OS’s have been developed in the **C programming language**, making them vulnerable to buffer overflows, arbitrary code execution etc.
	+ By default, Windows is not configured to run securely and require a proactiveimplementation of security practices in order to configure Windows to runsecurely. 
	+ Newly discovered vulnerabilities are not immediately patched by Microsoft and given the fragmented nature of Windows, many systems are left unpatched. 

- The frequent releases of new versions of Windows is also a contributing factor to exploitation, as many companies take a substantial length of time to upgrade their systems to the latest version of Windows and opt to use older versions that may be affected by an increasing number of vulnerabilities. 

- In addition to inherent vulnerabilities, Windows is also vulnerable to cross platform vulnerabilities, for example SQL injection attacks.

- Systems/hosts running Windows are also vulnerable to physical attacks like; theft, malicious peripheral devices etc. 

### Types of Windows Vulnerabilities

- Information disclosure - Vulnerability that allows an attacker to access confidential data.

- Buffer overflows - Caused by a programming error, allows attackers to write data to a buffer and overrun the allocated buffer, consequently writing data to allocated memory addresses

- Remote code execution - Vulnerability that allows an attacker to remotely execute code on the target system.

- Privilege escalation - Vulnerability that allows an attacker to elevate their privileges after initial compromise.

- Denial of Service (DOS) - Vulnerability that allows an attacker to consume a system/host’s resources (CPU, RAM, Network etc) consequently preventing the system from functioning normally. 