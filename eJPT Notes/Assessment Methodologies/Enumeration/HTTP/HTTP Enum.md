
- HTTP Port number - 80

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

```
nmap -p 80 <target-ip> -sV --script http-enum
```
