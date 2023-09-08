- We'll be using `metasploit` here.

### Bruteforcing logins

```
use auxiliary/scanner/mssql/mssql_login
```

### More enumeration

```
use auxiliary/admin/mssql/mssql_enum
```

- Returns database info like system configs and directory paths.

### Enumerating logins

```
use auxiliary/admin/msql/mssql_enum_sql_logins
```

### Running system commands

```
use auxiliary/admin/msql/mssql_exec
```

### Enumerating domain accounts

```
use auxiliary/admin/mssql/mssql_enum_domain_accounts
```

