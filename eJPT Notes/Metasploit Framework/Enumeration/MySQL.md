
+ MySQL is an open-source relational database management system based on SQL (Structured Query Language).

+ It is typically used to store records, customer data, and is most commonly deployed to store web application data.

+ MySQL utilizes TCP port 3306 by default, however, like any service it can be hosted on any open TCP port.

+ We can utilize auxiliary modules to enumerate the version of MySQL, perform brute-force attacks to identify passwords, execute SQL queries and much more.

### How to enumerate ?

1.  Start `postgresql` and `msfconsole`.

2. Using `portscan` module to confirm that `mysql` is running on port 3306.
```
use auxiliary/scanner/portsacn/tcp
```

3. Using `mysql_version` to determine the `mysql` version.
```
use auxiliary/scanner/mysql/mysql_version
```

4. Using `mysql_login` module to bruteforce the MySQL authentication.
```
use auxiliary/scanner/mysql/mysql_login
```
- Instead of bruteforcing usernames, we can use the username `root` to see if there's any password available. `set USERNAME root`.

5. If we successfully obtain the password, we can then use `mysql_enum` module to further enumerate the database server with legitimate credentials. 
```
use auxiliary/admin/mysql/mysql_enum
```
- This will help us enumerate crucial info such as configuration settings and password hashes of the current user and other users.

6. Using `mysql_sql` module to execute SQL queries in the server. This module requires legitimate credentials.
```
use auxiliary/admin/mysql/mysql_sql
```
- Set the `USERNAME` and `PASSWORD` options.
- Set the `SQL` option to the SQL query we want to execute. For example, we can use command `set SQL show databases;` to get a list of databases in the server.

7. Using `mysql_schemadump` to display all the databases and the tables that fall under the databases. 
```
use auxiliary/scanner/mysql/mysql_schemadump
```
- Set the `USERNAME` and `PASSWORD` options.
- We can then use the `mysql_sql` module to execute queries.

9. We can take a look at the information saved by `MSF` yet in the current workspace-
	+ Use command `services`, we can see the services that we have perform the enumeration on, which will of course show `mysql`.
	+ Use command `loot` to see the credentials we were able to get saved in text file. Which in this case, will be the `mysql schema` we were able to get. 
	+ Use command `creds` to dump out all the credentials we were able to gather through the enumeration modules in both plain text and hash. 

10. We can now successfully login-
```
mysql -h <target-ip> -u <user> -p
```

