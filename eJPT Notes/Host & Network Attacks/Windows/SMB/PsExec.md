### What is PsExec ?

- PsExec is a lightweight telnet-replacement developed by Microsoft that allows you execute processes on remote windows systems using any user’s credentials.

- PsExec authentication is performed via SMB.

- We can use the PsExec utility to authenticate with the target system legitimately and run arbitrary commands or launch a remote command prompt.

- It is very similar to RDP, however, instead of controlling the remote system via GUI commands are sent via CMD.

### How to exploit `SMB` with `PsExec` ?

* In order to utilise PsExec to gain access to a Windows target, we will need to identify  legitimate user accounts and their respective passwords or password hashes. 

- This can be done by leveraging various tools and techniques, however, the most common technique will involve performing an SMB login brute-force attack. 

* We can narrow down our brute-force attack to only include common Windows user accounts like: 
	+ Administrator

- After we have obtained a legitimate user account and password, we can use the credentials to authenticate with the target system via PsExec and execute arbitrary system commands or obtain a reverse shell.

### Exploiting SMB

1. Scan the network/web-app for SMB using `nmap`
```
nmap -sV -sC <ip>
```

2. If SMB is discovered, we can perform a brute-force attack using `metasploit`
```
use auxiliary/scanner/smb/smb_login
```

`USER_FILE` - /usr/share/metasploit-framework/data/wordlists/common_users.txt
``PASS_FILE`` - /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
*Set `VERBOSE` to false*

3. Executing CMD using `psexec`
```
psexec.py Administrator@<target-ip> cmd.exe
```

- The `psexec` utility is designed for Windows and comes in the form of an executable. Since executables are not compatible with Linux systems, we will utilize a Python version of the tool, known as `psexec.py`.
- We are executing `CMD.exe` to gain a command shell session on the target.
- In most cases, we'll want to target the administrator account, as it'll provide us with the highest access to the system. 
- By using legitimate Windows tools and avoiding exploits or malicious file uploads, we reduce the chances of detection, making this method highly effective.

### Using a `metasploit` module

- We'll be using a metasploit module that uses `psexec` to upload a malicious meterpreter payload to gain reverse shell access to the target system. 

```
use exploit/windows/smb/psexec
```

*Since we are uploading a malicious file, it has higher chances of getting detected.*