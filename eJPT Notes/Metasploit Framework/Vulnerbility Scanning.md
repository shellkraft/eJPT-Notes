
+ Vulnerability scanning & detection is the process of scanning a target for
vulnerabilities and verifying whether they can be exploited.

+ So far, we have been able to identify and exploit misconfigurations on target
systems, however, in this section we will be exploring the process of utilizing
auxiliary and exploit modules to scan and identify inherent vulnerabilities in
services, operating systems and web applications.

+ This information will come in handy during the exploitation phase of this course.

+ We will also be exploring the process of utilizing third party vulnerability scanning
tools like Nessus and how we can integrate Nessus functionality in to the MSF.

### How to perform vulnerability scanning ?

1. Scan the subnet using `nmap`.

2. Start `msfconsole`, set a global RHOST and create a workstation. 

3. Perform a scan with `db_nmap`.
```
db_nmap -sS -sV -O <ip>
```

4. Use command `services`, to check the services that have been enumerated.

5. `search` for exploits for the enumerated services. Check the exploit `info` to see if the version running in our target server is vulnerable to it.

6. We can use `searchspoloit` along with `grep`to look for `metasploit` exploits
```
searchsploit "<service-name>" | grep -e "Metasploit"
```

7. 