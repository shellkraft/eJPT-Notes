### What is WebDAV ?

- WebDAV (Web-based Distributed Authoring and Versioning) is a set of extensions to the HTTP protocol which allow users to collaboratively edit and manage files on remote web servers.

- WebDAV essentially enables a web server to function as a file server for collaborative authoring.

- WebDAV runs on top Microsoft IIS on ports 80/443.

- WebDAV is not specifically made for IIS, it can be used with other web servers like Apache. 


### How to exploit WebDAV ?

- The first step of the exploitation process will involve identifying whether WebDAV has been configured to run on the IIS web server. 

- We can perform a brute-force attack on the WebDAV server in order to identify legitimate credentials that we can use for authentication. 

- After obtaining legitimate credentials, we can authenticate with the WebDAV server and upload a malicious .asp payload that can be used to execute arbitrary commands or obtain a reverse shell on the target. 

### Using `nmap` to further enumerate `http`

```
nmap -sV -p 80 --script=http-enum <target_ip>
```

- This can be used to find out if the webDAV directory exists and if there's any interesting folders.
- To access webDAV directory, we might require authorisation.

### Using `hydra` to bruteforce authentication

```
hydra -L <user-file> -P <pass-file> <target-ip> http-get /webdav/
```

### How to use `DAVtest` ?


DAVTest tests WebDAV enabled servers by uploading test executable files to check what file formats does it support.

```
davtest -url http://<ip>/webdav
```

### How to use `cadaver`

Cadaver can be used to access the contents of `webdav` directory. It'll allow us to upload, download, edit or delete files from the directory.

```
cadaver http://<ip>/webdav
```

### Uploading a web shell using `cadaver` 

- We can upload a web shell 