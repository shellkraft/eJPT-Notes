
- A web server is software that is used to serve website data on the web.

- Web servers utilize HTTP (Hypertext Transfer Protocol) to facilitate the communication between clients and the web server.

- HTTP is an application layer protocol that utilizes TCP port 80 for communication. We can utilize auxiliary modules to enumerate the web server version, HTTP headers, brute-force directories and much more.

- Examples of popular web servers are; Apache, Nginx and Microsoft IIS.

### How to enumerate ?

1. Start the `postgresql` server and `msfconsole`.

2. Search for `http` `auxiliary` modules.

3. Use `http_version` module to detect the version of `http` service.
```
use auxiliary/scanner/http/http_version
```

4. Use `http_header` to get the `http` header.
```
use auxiliary/scanner/http/http_header
```

5. We'll now enumerate the `robots.txt` file.
```
use auxiliary/scanner/http/robots_txt
```

6. If we find directories that are set on `Disallow`, we can go ahead and curl those webpages.
```
curl http://<ip>/<directory>
```
- This will download and display the index of that file in html. 