- MS SQL - Microsoft SQL
- Port number - 1433

### Using `nmap` to enumerate basic info

```
nmap -p 1433 <ip> --script ms-sql-info
```

- Provides basic info like name of the server

### Enumerating MS SQL NTLM info with `nmap`

```
nmap -p 1433 <ip> --script ms-sql-ntlm-info --script-args mssql.instance-port=1433
```

- Provides NetBios domain and computer name
- Provides product version. 
- Provides DNS computer and domain name. 

