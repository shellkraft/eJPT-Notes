+ FTP (File Transfer Protocol) is a protocol that uses TCP port 21 and is used to facilitate file sharing between a server and client/clients.

+ It is also frequently used as a means of transferring files to and from the directory of a web server.

+ `vsftpd` is an FTP server for Unix-like systems including Linux systems and is the default FTP server for Ubuntu, CentOS and Fedora.

+ `vsftpd V2.3.4` is vulnerable to a command execution vulnerability that is facilitated by a malicious backdoor that was added to the `vsftpd` download archive through a supply chain attack. 

### How to exploit ?

1. Perform a scan with `db_nmap`.

2. Exploiting `VSFTPD V2.3.4` to execute backdoor commands.
```
use exploit/unix/ftp/vsftpd_234_backdoor
```

3. Initially we'll get a command shell session