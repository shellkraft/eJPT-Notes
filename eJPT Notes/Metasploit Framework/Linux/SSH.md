
+ SSH (Secure Shell) is a remote administration protocol that offers encryption and is the successor to Telnet.

+ It is typically used for remote access to servers and systems.

+ SSH uses TCP port 22 by default, however, like other services, it can be configured to use any other open TCP port.

+ `libssh` is a multiplatform C library implementing the SSHv2 protocol on client and server side.

+ `libssh` V0.6.0-0.8.0 is vulnerable to an authentication bypass vulnerability in the `libssh` server code that can be exploited to execute commands on the target server.

### How to exploit `libssh`?

1. Scan the target with `db_nmap`.

2. Exploiting the vulnerable `libssh` service.
```
use auxiliary/scanner/ssh/libssh_auth_bypass
```
- Set `SPAWN_PTY` option to `true`. This will allow us to spawn a terminal session.

3. Upgrade the current session to `meterpreter` session using `shell_to_meterpreter` module.