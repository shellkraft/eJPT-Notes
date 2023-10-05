
+ An HTTP File Server (HFS) is a web server that is designed for file & document sharing. 

+ HTTP File Servers typically run on TCP port 80 and utilize the HTTP protocol for underlying communication.

+ Rejetto HFS is a popular free and open source HTTP file server that can be setup on both Windows and Linux.

+ Rejetto HFS V2.3 is vulnerable to a remote command execution attack.

+ MSF has an exploit module that we can utilize to gain access to the target system hosting the HFS. 

### How to exploit ?

1. Start `postgresql` and `msfconsole`.

2. Create a workspace.

3. Use `db_nmap` module to scan the target IP, so that the scan results are stored inside our current workspace.

4. We can now search for exploits for the `rejetto` HFS.

5. We can always customise the payload architecture for every exploit module. By default the `rejetto_hfs_exec` exploit module uses 32 bit payload.
```
set PAYLOAD windows/x64/meterpreter/reverse_tcp
```

