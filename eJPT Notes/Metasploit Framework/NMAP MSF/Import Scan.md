
### How to import `nmap` scan into `MSF` ?

1. Start `msfconsole` with `PostgreSQL`
```
service postgersql start && msfconsolw
```

2. Check status of `msfdb`. - `db_status`

3. Create a new workspace.

4. Import the scan results. 
```
db_import <xml_file_path>
```

5. Confirm that it is successfully imported by using `hosts` command. It should now display the RHOST and OS name. We can also use the `services` command to display the services that `NMAP` discovered in its scan.

### How to perform `NMAP` scan from `MSF` ?

1. Create a new workspace.

2. Enter the command to perform the scan.
```
db_nmap -Pn -sV -O <ip>
```
- This will perform an `NMAP` scan within `MSF`. 
- The scan results will be automatically imported within the `msfdb` within our current workspace.



