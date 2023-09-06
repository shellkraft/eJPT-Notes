
### Using `metasploit`

```
use auxiliary/scanner/mysql/mysql_login
```

- Set `stop_on_success` to true
- Wordlist path - `/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt`

### Using `hydra`

```
hydra -l <username> -P <path_to_wordlist> <target-ip> mysql
```