### Server Message Block (SMB)

Windows implementation of a file share. Used for sharing access to files, printers, serial ports, and data on a network.

Port number - 445/TCP

*Netbios used to exist in older Windows versions. Used to setup session for SMB.*

# Command to setup SMB

### For connecting:
```
net use Z: \\<Machine IP>\C$ <SMB_PASSWORD> /user:<USERNAME>
```

- `C$` - Drive to host
### For disconnecting:
```
net use * /delete
```

# SMB Enumeration 

*We can use NMAP to scan for SMB ports and perform enumeration on it.*

**Nmap command to enum SMB:**

```
nmap -p 445 --script smb-protocols <Machine IP>
```

*The scan results might return the SMB version. For example, SMBv1 was used by WannaCry Ransomware.*

```
nmap -p 445 --script smb-security-mode <Machine IP>
```

- Command to check current SMB sessions:
```
nmap -p 445 --script smb-enum-sessions <Machine IP>
```

- Command to get authenticated SMB session:
```
nmap -p 445 --script smb-enum-sessions --script-args smbusername=<USERNAME>,smbpassword=<PASSWORD> <Machine IP>
```

- Command to check the files that are shared using SMB (We can use `--script-args` to login as admin as well.):
```
nmap -p 445 --script smb-enum-shares <Machine IP>
```

- Command to enum the users & their configs: 
```
nmap -p 445 --script smb-enum-users --script-args smbusername<USERNAME>,smbpassword=<PASSWORD> <Machine IP>
```

Other switches:
``
``-smb-server-stats`` = Enums server info like, number of attempts to login.

