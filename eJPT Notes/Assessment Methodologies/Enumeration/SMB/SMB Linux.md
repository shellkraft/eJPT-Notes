### Using Metasploit for SMB version scan:
```
use auxillary/scanner/smb/smb_version
```

### Using `nmblookup`:
```
nmblookup -A <Target IP>
```
- *Performs netBIOS protocol to connect and perform the recon.*
- `-A` - Lookup by IP.

### Using `smbclient`
```
smbclient -L <IP> -N
```

`-L` - Host addr
`-N` - NULL session (No username or password)
