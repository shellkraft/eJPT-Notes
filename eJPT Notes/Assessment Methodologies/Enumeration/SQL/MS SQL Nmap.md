- MS SQL - Microsoft SQL
- Port number - 1433

### Using `nmap` to enumerate basic info

```
nmap -p 1433 <ip> --script ms-sql-info
```

- Provides basic info like name of the server

### Enumerating MS SQL NTLM info 

```
nmap -p 1433 <ip> --script ms-sql-ntlm-info --script-args mssql.instance-port=1433
```

- NTLM - NT LAN Manager (Windows authentication manager)
- Provides NetBios domain and computer name
- Provides product version. 
- Provides DNS computer and domain name. 

### Bruteforcing MS SQL logins 

```
nmap -p 1433 <ip> --script ms-sql-brute --script-args userdb=<user_file>,passdb=<pass-file>
```

### Checking for NULL passwords

```
nmap -p 1433 <ip> --script ms-sql-empty-password
```

### Running MS SQL query 

```
nmap -p 1433 <ip> --script ms-sql-query --script-args mssql.username=<user>,mssql.password=<pass>,ms-sql-query.query="SELECT * FROM master..syslogins" <host> -oN output.txt
```

- Outputting it to a text file for better readability.

### Dumping hashes

```
nmap -p 1433 <ip> --script ms-sql-dump-hashes --script-args mssql.username=<user>,mssql.password=<pass>
```

