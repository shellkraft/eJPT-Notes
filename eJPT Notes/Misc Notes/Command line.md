1) What is that command ? 
- use ``whatis`` command to find out - ``whatis nslookup``

2) How to open host file in Linux ?
```
sudo nano /etc/hosts
```

3) What is a host file tho ?
- It contains the list of hostnames and Domain names and their corresponding IP addresses. 
- U can make changes in the host file to map an IP address to a local domain. (Cannot be accessed by the internet). 
```
192.168.0.1 router.admin
```

4) Extract files using `gzip` and `tar`
```
gzip -d file.gz
```

```
tar -xf file.tar.gz
```

5) What's `curl` ?
`curl`: This is a command-line tool used to transfer data to or from a server using various network protocols, such as HTTP, HTTPS, FTP, etc.