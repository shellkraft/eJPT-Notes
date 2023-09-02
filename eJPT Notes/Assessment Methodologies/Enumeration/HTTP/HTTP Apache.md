- Runs on Linux

### Using `nmap`

```
nmap -p 80 -sV --script banner <target-ip>
```

- **Banner**- Banner is the info a computer receives the first time they connect to a machine.

### Using `metasploit`

- Performs a http version scan:
```
use auxiliary/scanner/http/http-version
```

### Using `curl`

```
curl <target-ip> | more
```

