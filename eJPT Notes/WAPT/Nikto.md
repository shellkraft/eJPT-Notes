
### What is `Nikto` ?

_Nikto_ is a pluggable web server and CGI scanner written in Perl, using rfp's LibWhisker to perform fast security or informational checks.

### How to use ?

1. We can perform a basic scan on the target using the following command.
```
nikto -h http://<target-ip>
```

2. We can use `Nikto` to check for File Inclusion vulnerability by setting the `Tuning` to 5.
	- A directory traversal attack is ==a type of HTTP exploit that allows an attacker to access restricted files and directories==. It's also known as a path traversal attack or a dot dot slash attack.
```
nikto -h http://<full-url-to-file> -Tuning 5 -Display V
```
- We are setting Display to V to turn on verbose.
- This will use this exploit to find restricted pages for us.
- We can use this flaw to access file like `/etc/passwd` by manipulating the URL. 
```
website.com/index.php?page=../../../../../../etc/passwd
```

3. We can also output the result of the scan in a HTML file for better readability. 
```
nikto -h http://<full-url-to-file> -Tuning 5 -Display V -o nikto.html -Format htm
```

