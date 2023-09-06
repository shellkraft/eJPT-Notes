*MySQL is the common type of DBMS. It usually runs on Linux or Unix.*

- **Port number -** 3306

### Using `mysql` command to login in the database

```
mysql -h <host-IP> -u <username> 
```

### Command to list databases
```
show databases;
```

### Command to enter a database
```
use books;
```
*After we enter `books` database, we can count the number of authors in it.*

### Command to count number of rows in a table
```
select count(*) from authors;
```

### Command to show the table
```
select * from authors;
```

