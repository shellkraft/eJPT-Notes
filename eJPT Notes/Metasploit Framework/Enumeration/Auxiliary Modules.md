
+ Auxiliary modules are used to perform functionality like scanning, discovery and fuzzing.

+ We can use auxiliary modules to perform both TCP & UDP port scanning as well as enumerating information from services like FTP, SSH, HTTP etc

+ Auxiliary modules can be used during the information gathering phase of a penetration test as well as the post exploitation phase.

+ We can also use auxiliary modules to discover hosts and perform port scanning on a different network subnet after we have obtained initial access on a target system. 

### Pivoting with `MSF` Basics

1. Start `msfconsole` with `postgresql` database service.

2. Create a new workspace.

3. Portscan with an auxiliary module.
```
use auxiliary/scanner/portscan/tcp
```

4. In our case, port 80 is open, which indicates presence of a web server. 

5. We can use `curl` to see the `html` of the website. This way, we can potentially identify the service running in the web server. 

6. Search the service name, find the exploit module and exploit the web server.

7. After we get a `meterpreter` session, enter the `shell` session using `/bin/bash -i`.

8. Check the network information using `ifconfig`. We see that the target has another interface `eth1` and this has a totally different IP address, which indicates that it is part of a different subnet. 

9. Now that we have identified the subnet of this particular local network, we can add the route within `meterpreter`
```
run autoroute -s <ip-addr> 
```

- The `autoroute` command in Metasploit is used to manage the routing of traffic through a compromised system to reach other subnets or hosts. This can be especially useful when you have gained access to a network and want to pivot through the compromised system to reach other internal network segments.

10. We can now background the current session. To perform a port scan on the IP address which we just discovered. 

11. Since we have the route, we can perform a port scan through the first system we exploited. 

12. We can now type `back` to exit the module. And now use another module to perform an UDP scan.
```
use auxiliary/scanner/discovery/udp_sweep 
```

