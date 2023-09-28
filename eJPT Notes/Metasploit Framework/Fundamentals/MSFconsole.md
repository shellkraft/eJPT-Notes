
+ Before we can start using the Metasploit Framework for penetration testing, we need to get an understanding of how to use `MSFconsole`.

+ The Metasploit Framework Console (`MSFconsole`) is an easy-to-use all in one interface that provides you with access to all the functionality of the Metasploit Framework. 

+ We will be utilizing `MSFconsole` as our primary `MSF` interface for the rest of the course.

### MSF Module Variables

+ MSF modules will typically require information like the target & host address and port in order to initiate a remote exploit/connection.

+ These options can be configured through the use of `MSF` variables.

+ `MSFconsole` allows you to set both local variable values or global variable values.

| Variable | Purpose |
|-----------------|-----------------|
| LHOST   | Stores IP of attacker system   |
| LPORT   | Stores port  number of attacker system   |
| RHOST   | Stores IP of target system/server   |
| RHOSTS   | Specify IP of multiple target systems or network ranges   |
| RPORT   | Store the port number that we are targeting in the target system   |

### Basic commands in `msfconsole`

- We can see the help menu of the `search` command using `search -h`
- We can use search like this-
```
swarch cve:2017 type:exploit platform:-windows
```
- Use `connect` command for banner grabbing
```
connect <ip> <port>
```
- We can use `setg` command to set variable as global.
```
setg RHOSTS <IP>
```

