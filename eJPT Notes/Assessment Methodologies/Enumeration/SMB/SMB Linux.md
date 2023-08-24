### Using Metasploit for SMB version scan:
```
use auxillary/scanner/smb/smb_version
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

### Using `rpcclient`
```
rpcclient -U "" -N <IP>
```

`-U` - Username
`-N` - No password

### Using `enum4linux`
```
enum4linux -o <IP>
```

`-o` - Get OS info.  

*We can use it to check OS version, to check if it allows for NULL sessions or check for usernames.*

