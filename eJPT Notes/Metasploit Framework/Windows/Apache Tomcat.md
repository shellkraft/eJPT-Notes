
+ Apache Tomcat, also known as Tomcat server, is a popular, free and open source Java
servlet web server.

+ tis used to build and host dynamic websites and web applications based on the Java
software platform.

+ Apache Tomcat utilizes the HTTP protocol to facilitate the underlying communication
between the server and clients.

+ Apache Tomcat runs on TCP port 8080 by default.

### Difference between Apache and Apache Tomcat

+ The standard Apache HTTP web server is used to host static and dynamic websites
or web applications, typically developed in PHP.

+ The Apache Tomcat web server is primarily used to host dynamic websites or web
applications developed in Java.

+ Apache Tomcat V8.5.19 is vulnerable to a remote code execution vulnerability that
could potentially allow an attacker to upload and execute a JSP payload in order to
gain remote access to the target server.

+ We can utilize a prebuilt MSF exploit module to exploit this vulnerability and
consequently gain access to the target server.

### How to exploit ?

1. Perform a port scan with `db_nmap`.

2. We can to the browser and go to port 8080 of the target IP to confirm that Apache Tomcat is running.

3. Gaining `meterpreter` session by uploading malicious `.jsp` file.
```
use exploit/multi/http/tomcat_jsp_upload_bypass
```
- Set payload - `set payload java/jsp_shell_bind_tcp`
- Set system shell to `cmd` - `set SHELL cmd`
- If the exploit doesn't run, we can terminate it and re-run it. This particular exploiyt might take a few tries to get working.

4. We can background this session, and check the session list using `sessions`. We can see that the type of payload specified is `java/linux`. We need to upload a `msfvenom` payload. 

5. Create an `msfvenom` payload, send it to the target by using `SimpleHTTPServer` of Python.

6. Use `certutil` to install the payload on the target system. Run the payload.