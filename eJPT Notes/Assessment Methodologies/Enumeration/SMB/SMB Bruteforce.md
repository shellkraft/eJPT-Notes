
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

### What are Pipes ?

- __Pipe__ - In networking, a "pipe" is like that telephone line—it's a way for these computers to send information back and forth. Just as you talk into one end of the phone and your friend hears your voice on the other end, computers can send data through a pipe to another computer on the network.

- **Named Pipes** - A special type of pipe where you not only send messages but also give the pipe a specific name, like "ChatPipe." This way, different programs on the same computer can communicate with each other using this named pipe. It's like having a designated line for specific types of communication. Example - Printers use named pipe "spools" to handle printing requests.

### Using pipes to access other services:

- *We'll use metasploit:*
```
use auxiliary/scanner/smb/pipe_auditor
```

