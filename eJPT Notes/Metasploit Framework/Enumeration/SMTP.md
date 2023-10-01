
+ SMTP (Simple Mail Transfer Protocol) is a communication protocol that is used for the transmission of email.

+ SMTP uses TCP port 25 by default. It is can also be configured to run on TCP port 465 and 587.

+ We can utilize auxiliary modules to enumerate the version of SMTP as well as user accounts on the target system.

### How to enumerate ?

1. Start the `postgresql` server and `msfconsole`.

2. Create a separate workspace for this.

3. Set a global RHOST. 

4. Since SMTP can run on different ports, it is recommended to run a port scan. 

5. Use `smtp_version` module to identify the SMTP version.
```
use auxiliary/scanner/smtp/smtp_version
```
- It will also tell us the domain of the SMTP server.

7. Using `smtp_enum` module to perform user enumeration.
```
use auxiliary/scanner/smtp/smtp_enum
```
- This module uses SMTP service internal commands such as `VRFY` and `EXPN` to reveal the list of valid users. Use command `info` to learn more.
- Since we now know the usernames, it can now help us stage other attacks, we can use these to perform a SSH bruteforce. 
