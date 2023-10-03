
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

7. Exploit the vulnerable service using the `metasploit` module.

### Using `metasploit-autopwn` tool 

- `Metasploit-autopwn` is a tool that automates the process of vulnerability scanning of each service running on the target machine. It provides the list of exploits the services in the target machine is vulnerable to.
https://github.com/hahwul/metasploit-autopwn

#### How to use ?

1. Download the `db_autopwn.rb` file.
```
wget https://raw.githubusercontent.com/hahwul/metasploit-autopwn/master/db_autopwn.rb
```

2. Move `db_autopwn.rb` file into `metasploit` plugin directory.
```
sudo mv db_autopwn.rb /usr/share/metasploit-framework/plugins
```

3. Start `msfconsole`.

4. Use command `load db_autopwn` to load the plugin.

5. We can then type `db_autopwn` to check the help menu.

6. We can enumerate the exploits for all the 



