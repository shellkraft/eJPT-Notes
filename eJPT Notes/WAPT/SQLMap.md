
### What is `SQLMap` ?

- `sqlmap` is an open source penetration testing tool that automates the process of detecting and exploiting SQL injection flaws and taking over of database servers

### How to use `SQLMap` ?

1. Use Burp to intercept and analyse the header info of the target web-page. In our case, we are using `bWAPP` for testing SQL injection.

2. Login into the page to get the PHP session ID (cookie). 

3. Now that we've logged in as an authenticated user, we can access the SQL database from a basic search prompt. In our case, the `bWAPP` web-page for testing SQLI has a search prompt.

4. We'll use the search prompt to search for something and record the format in which the GET request for our prompt was sent using Burp. We can also find it in the URL.

GET /==sqli_1.php?title=joe&action=search== HTTP/1.1


6. To use SQLMap we can use the following command.
```
sqlmap -u "http://<target-ip>/"
```