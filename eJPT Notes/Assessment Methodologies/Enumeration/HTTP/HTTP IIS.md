
- HTTP Port number - 80
- IIS - Internet Information Services (_IIS_)
- Runs on Windows

### Using `whatweb`

```
whatweb <IP>
```

*We can check if XSS protection is enabled or not.*

### Using `httpie`

```
http <ip/website> 
```

- *Enumerates header information.*
- *If the header info contains file type ASPx, then the OS might be Microsoft. *

### Using `dirb`

```
dirb http://<IP>
```

*Enumerating directories.*

### Using `browsh`

```
browsh --startup-url http://<IP>
```

- *Useful for opening websites in a CLI environment using a URL.*
- *Since it renders website in a terminal, the results might not be desirable.*

### Using `nmap`

- For directory enum:
```
nmap -p 80 <target-ip> -sV --script http-enum
```


- *Fetches HTTP header info along with other info:*
```
nmap -p 80 <target-ip> -sV --script http-headers
```


- *Enumerating the methods we can use on the webpage:*
```
nmap --script http-methods --script-args http-methods.url-path=/webdav/ <IP>
```


- *Helps to identify webdav installations.*
```
nmap --script http-webdav-scan --script-args http-methods.url-path=/webdav/ <IP>
```

