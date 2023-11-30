
### What is `SQLMap` ?

- `sqlmap` is an open source penetration testing tool that automates the process of detecting and exploiting SQL injection flaws and taking over of database servers

### `SQLMap` for GET/Search 

1. Use Burp to intercept and analyse the header info of the target web-page. In our case, we are using `bWAPP` for testing SQL injection.

2. Login into the page to get the PHP session ID (cookie). 

3. Now that we've logged in as an authenticated user, we can access the SQL database from a basic search prompt. In our case, the `bWAPP` web-page for testing SQLI has a search prompt.

4. We'll use the search prompt to search for something and record the format in which the GET request for our prompt was sent using Burp. We can also find it in the URL.

```
GET /sqli_1.php?title=joe&action=search HTTP/1.1
```


6. To use SQLMap we can use the following command.
```bash
sqlmap -u "http://<target-ip>/sqli_1.php?title=joe&action=search" --cookie "PHPSESSID=<cookie>; security_level=0" -p title 
```
- In this command we are targeting the `title` parameter using the `-p` option.
- It'll test for `SQLI` in the GET parameter `title`.

7. If the parameter `title` is vulnerable, it'll provide us with the SQL payloads which the `title` parameter is vulnerable to. We can copy one of the payloads. 

8. Send the initial GET request we captured for the search prompt in Burp to the repeater. 

9. In the repeater we will modify the GET request and paste our copied payload in it. Check whether we've pasted the payload in the correct format. 

10. We will now send the new request and check the Raw HTML response header. If the payloads work, we shouldn't get any errors. 

11. In case the payloads do not work, we can try different approaches by using the following options with the previous command. 
	+ Use `--dbs` options to check what databases are accessible.
	+ Use `-D <database-name> --tables` to check the tables in a particular database. 
	+ Now that we've identified the tables, we can use this command to check the columns of a particular table `-D <database> -T <table-name> --columns`. 
	+ We can dump the contents of a column, using `-C column1,column2,column3 --dump`. We need to specify the database name and the table name for this command to work.

### `SQLMap` for POST/Search


1. Turn intercept on and use the search prompt to search for something and record the format in which the POST request for our prompt was sent using Burp. We can also find it in the URL.

2. Usually for GET request we pass variables in the URL, but for POST request we are going to pass it in the body of our POST request header.  

3. Save this POST request to a file using the `Copy to All` button in the `Action` menu. 

4. Now we can use `sqlmap` on the request file we just saved.
```bash
sqlmap -r <filename> -p title
```
- We are targeting the `title` parameter. 
- This will provide us with the payloads. We can use the payloads using the Burp repeater.

5. Send the initial POST request to the repeater and use a payload in the request header. We can now send this modified request and analyse the response header. 