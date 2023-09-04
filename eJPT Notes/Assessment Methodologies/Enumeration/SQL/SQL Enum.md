
### Using `metasploit` to enumerate directories

- Metasploit module to enumerate writable directories in the system using MySQL:
```
use auxiliary/scanner/mysql/mysql_writable_dirs
```

- **WordList path** - /usr/share/metasploit-framework/data/wordlists/directory.txt
- Set verbosity to `false` to avoid getting spammed with too many messages. 
- To show more options use command `advanced`
- Instead of using `set <RHOSTS>`, we can use `setg <RHOSTS>` to set it as a global variable.

**How does this module work ?**

- This Metasploit module doesn't enumerate directories in the traditional sense but rather checks if MySQL has write access to specific directories using SQL queries to create temporary files 
