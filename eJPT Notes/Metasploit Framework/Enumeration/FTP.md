
+ FTP (File Transfer Protocol) is a protocol that uses TCP port 21 and is used to facilitate file sharing between a server and client/clients.

+ It is also frequently used as a means of transferring files to and from the directory of a web server.

+ We can use multiple auxiliary modules to enumerate information as well as perform brute-force attacks on targets running an FTP server.

+ FTP authentication utilizes a username and password combination, however, in some cases an improperly configured FTP server can be logged into anonymously.

### How to enumerate FTP with `MSF` ?

1. Start the `postgresql` server and `msfconsole`.

2. Use the `MSF` TCP Portscan module to check if port 21 is open or not.
```
use auxiliary/scanner/portscan/tcp
```

3. This module won't show us the FTP service version, which makes it difficult for us to look for exploits. For that reason, we'll be using `ftp_version` module.
```
use auxiliary/scanner/ftp/ftp_version
```

4. We can now use `anonymous` module to check if anonymous login is allowed or not.
```
use auxiliary/scanner/ftp/anonymous
```
- This will check if login with NULL session is allowed or not.
- Chances are this won't be allowed.

5. Now that we know the FTP version, we can look for exploits pertinent to that particular version. If exploit is not available, we can proceed with bruteforcing the FTP credentials.
```
use auxiliary/scanner/ftp/ftp_login
```

- A bruteforce might cause a service to shut down for some time. If that happens, please wait for some time for the service to restart. 

6. If we get the credentials, we can login using `ftp <target-ip>`.
	+ We can now download files using `get <filename>`

