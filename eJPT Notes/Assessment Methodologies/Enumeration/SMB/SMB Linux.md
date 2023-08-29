### Using Metasploit for SMB version scan:
```
use auxiliary/scanner/smb/smb_version
```

### Using `nmblookup`:
```
nmblookup -A <Target IP>
```
- *Performs netBIOS protocol to connect and perform the recon.*
- *Obtain the NetBIOS computer name of samba server.*
- `-A` - Lookup by IP.

### Using `smbclient`
```
smbclient -L <IP> -N
```

`-L` - Host addr
`-N` - Check for NULL session (No username or password)

*We can also use `smbclient` to access shared folders:*
```
smbclient //192.4.17.3/Public -N
```

*To check the contents of a file, we first need to use `get file` and then `cat file`*

*We can use `smbclient`  to login as a particular user:*
```
smbclient //192.4.17.3/jane -U jane <password>
```
 
### Using `rpcclient`
```
rpcclient -U "" -N <IP>
```

`-U` - Username
`-N` - No password
`lookupnames admin` - Use this on rpcclient shell to look for specific users.

*We can also enum domain groups using `rpcclient`*
```
rpcclient -U "" -N <IP> enumdomgroups
```
### Using `enum4linux`
```
enum4linux -o <IP>
```

`-o` - Get OS info.  

*We can use it to check OS version, to check if it allows for NULL sessions or check for usernames.*

### What are SIDs (Security Identifiers) ?

SIDs are __*unique identifiers*__ assigned to security principals in a Windows environment, such as users, groups, and computer accounts. When you want to identify a user or group within an SMB-enabled network, you often encounter SIDs associated with them.

### Enumerating SIDs with `enum4linux`
```
enum4linux -r -u "admin" -p "password1" <IP> 
```
