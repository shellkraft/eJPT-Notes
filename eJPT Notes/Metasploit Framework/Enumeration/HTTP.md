
- A web server is software that is used to serve website data on the web.

- Web servers utilize HTTP (Hypertext Transfer Protocol) to facilitate the communication between clients and the web server.

- HTTP is an application layer protocol that utilizes TCP port 80 for communication. We can utilize auxiliary modules to enumerate the web server version, HTTP headers, brute-force directories and much more.

- Examples of popular web servers are; Apache, Nginx and Microsoft IIS.

### How to enumerate ?

1. Start the `postgresql` server and `msfconsole`.

2. Search for `http` `auxiliary` modules.

3. Use `http_version` module to detect the version of `http` service.
```
use auxiliary/scanner/http/http_version
```

4. Use `http_header` to get the `http` header.
```
use auxiliary/scanner/http/http_header
```

5. We'll now enumerate the `robots.txt` file.
```
use auxiliary/scanner/http/robots_txt
```

6. If we find directories that are set on `Disallow`, we can go ahead and curl those webpages to check the html code of those directories to get a better understanding.
```
curl http://<ip>/<directory>
```
- This will download and display the index of that file in html. 

7. Use `dir_scanner` module to bruteforce directories. 
```
use auxiliary/scanner/http/dir_scanner
```

8. We can use `files_dir` to bruteforce files in the webserver. This will help us discover hidden files.
```
use auxiliary/scanner/http/files_dir
```
- We can set the `EXT` option, if we are looking for a specific file type. 

9. In our case, we've discovered a directory that requires us to login in order to to access it's contents. We'll now use `http_login` module to bruteforce the login form.
```
use auxiliary/scanner/http/http_login
```
- First we need to set the `AUTH_URI` option to the directory which has authentication enabled. 
- If the default wordlists that are automatically set for the variable `PASS_FILE` and `USER_FILE` do not work, we'll use our own wordlist.
 User File -  ``/usr/share/metasploit-framework/data/wordlists/namelist.txt``
 Pass File - ``/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
- We'll also remove the value of `USERPASS_FILE`. 

10. We will now use the `apache_userdir_enum` module to bruteforce valid usernames in the server.
```
use auxiliary/scanner/http/apache_userdir_enum
```

11. We can now use the usernames we found to bruteforce the passwords using `http_login` module.