
+ SSH (Secure Shell) is a remote administration protocol that offers encryption and is the successor to Telnet.

+ It is typically used for remote access to servers and systems.

+ SSH uses TCP port 22 by default, however, like other services, it can be configured to use any other open TCP port.

+ We can utilize auxiliary modules to enumerate the version of SSH running on the target as well as perform brute-force attacks to identify passwords that can consequently provide us remote access to a target.

### How to enumerate ?

1. Start the `postgresql` server and `msfconsole`.

2. Create a separate workspace for this.

3. Set a global RHOST. 

4. Using `ssh_version` to check the version of SSH being used.
```
use auxiliary/scanner/ssh/ssh_version
```

5. Use `ssh_login` module to bruteforce password authentication in SSH.
```
use auxiliary/scanner/ssh/ssh_login
```

6. Use `ssh_login_pubkey` module to bruteforce authentication with public key. 
```
use auxiliary/scanner/ssh/ssh_login_pubkey
```

7. A command shell session will be opened with successful bruteforce. We can interact it with, with `session <session-id>`

8. If our initial bruteforce wasn't successful, we can use `ssh_enumusers` module to enumerate the users and narrow down the bruteforce. 
```
use auxiliary/scanner/ssh/ssh_enumusers
```


