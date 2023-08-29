### Using `netcat` to enumerate:
```
nc <Target-IP> 22
```
*We can get the banner info using `nc` which contains the SSH version.*

### Using `nmap` to enumerate: 
```
nmap <target-ip> -p 22 --script ssh2-enum-algos
```

*The `ssh2-enum-algos` script is designed to enumerate and display the supported algorithms (ciphers, key exchange methods, MACs, etc.) that an SSH server supports. This can be useful for security assessment and checking the cryptographic algorithms used by the SSH server.*

### Enumerating SSH RSA Host-key:

```
nmap -p 22 <machine-ip> --script ssh-hostkey --script-args ssh_hostkey=full
```

*Host keys are a form of public key cryptography and are used to establish the identity and authenticity of the SSH server you're connecting to.*

### Check for weak auth methods:

```
nmap -p 22 <machine-ip> --script ssh-auth-methods --script-args="ssh.user=<username>"
```

*We can discover `none_auth` methods, which we can use to gain access.*

