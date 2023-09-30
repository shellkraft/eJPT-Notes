+ SMB (Server Message Block) is a network file sharing protocol that is used to facilitate the sharing of files and peripherals between computers on a local network (LAN).

+ SMB uses port 445 (TCP). However, originally, SMB ran on top of NetBIOS using port 139.

+ SAMBA is the Linux implementation of SMB, and allows Windows systems to access Linux shares and devices.

+ We can utilize auxiliary modules to enumerate the SMB version, shares, users and perform a brute-force attack in order to identify users and passwords.


### How to enumerate ?

1. Start `postgresql` and `msfconsole`.

2. Search for SMB modules - `search type:auxiliary name:smb`

3. We can now use the `smb_version` module to check the SMB version.
```
use auxiliary/scanner/smb/smb_version
```

4. We can use `smb_enumusers` to enumerate the SMB users.
```
use auxiliary/scanner/smb/smb_enumusers
```

5. Use `smb_shares` module to enumerate the SMB shares.
```
use auxiliary/scanner/smb/smb_enumshares
```
- Set the `ShowFiles` option to `true`

6. Brute-force SMB password for a particular user.
```
use auxiliary/scanner/smb/smb_login
```

- Set the `SMBUser` option to a user we discovered using `smb_enumusers`.

7. Using `smbclient` to check the shares.
```
smbclient -L \\\\<ip>\\ -U <username>
```

8. We can now access a share and login using SMB.
```
smbclient -L \\\\<ip>\\<share> -U <username>
```

- We can download a file using `get <file>`

