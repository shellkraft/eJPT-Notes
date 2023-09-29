
+ Auxiliary modules are used to perform functionality like scanning, discovery and fuzzing.

+ We can use auxiliary modules to perform both TCP & UDP port scanning as well as enumerating information from services like FTP, SSH, HTTP etc

+ Auxiliary modules can be used during the information gathering phase of a penetration test as well as the post exploitation phase.

+ We can also use auxiliary modules to discover hosts and perform port scanning on a different network subnet after we have obtained initial access on a target system. 

### Pivoting with `MSF` Basics

1. Start `msfconsole` with `postgresql` database service.

2. Create a new workspace.

3. Portscan with an auxiliary module.
```
use auxiliary/scanner/portsacn/tcp
```

4. In our case, port 80 is open, which indicates presence of a web server. 

5. We 



