
### HTTP Method Enumeration

1. Open the web app in the browser and analyse the source code. 

2. Check if there's a login page available. 

3. Use `dirb` to enumerate the directories. 

4. Use `curl` with different methods to check the source code.
```
curl -X GET <target-ip>
```

5. We can send a HTTP HEAD request to obtain the response header. 
```
curl -I <target-ip>
```

6. Use the OPTIONS method to check what methods are allowed by the web app.
```
curl -X OPTIONS <target-ip> -v
```
- If we use a method which isn't allowed, we should get a `METHOD NOT ALLOWED` error.

7. Similarly, we can use OPTIONS to check the methods for different directories. In our case, it seems that the `/uploads/` directory allows file uploads. We confirm that by uploading a file using `curl`.
```
curl <target-ip>/uploads/ --upload-file <filename>
```
- This successfully uploads the file, this indicates that file upload is indeed allowed.

8. We can delete a file using the DELETE method.
```
curl -X DELETE <target-ip>/uploads/<filename>
```

### Enumeration with Burp Suite

1. Open your browser and and turn on Burp proxy from the `FoxyProxy` menu. Learn how to configure Burp with `FoxyProxy` from the following video.
https://youtu.be/2UMwYmKhu2w?si=hxB7WsmBbl0rsF2g

2. Go to Burp and turn intercept on to capture traffic. By doing this we'll get the raw header information which we can send to the repeater to tweak around with.

3. In the repeater, we can change the initial GET method in the request header to OPTIONS to check the methods that are allowed.

4. We can also modify the directory in the request header to something like `/login.php` and send it. This will help us understand whether `/login.php` directory exists or not.