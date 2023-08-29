### What's FTP Anon

If FTP server running on the remote host allows anonymous logins, any remote user may connect and authenticate to the server without providing a password or unique credentials. This allows the user to access any files made available by the FTP server.

- Using `nmap` to check for FTP anonymous login. 
```
nmap <IP> -P 21 --script ftp-anon
```

- *If it is allowed, we can login with username `anonymous` and blank password.*
