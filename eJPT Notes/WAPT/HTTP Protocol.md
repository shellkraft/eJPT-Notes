
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

