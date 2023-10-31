- We'll be using `metasploit` here.

### Bruteforcing logins

```
use auxiliary/scanner/mssql/mssql_login
```

- Password list - `/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt`
### More enumeration

```
use auxiliary/admin/mssql/mssql_enum
```

- Returns database info like system configs and directory paths.

### Enumerating logins

```
use auxiliary/admin/mssql/mssql_enum_sql_logins
```

### Running system commands

```
use auxiliary/admin/mssql/mssql_exec
```

### Enumerating domain accounts

```
use auxiliary/admin/mssql/mssql_enum_domain_accounts
```

