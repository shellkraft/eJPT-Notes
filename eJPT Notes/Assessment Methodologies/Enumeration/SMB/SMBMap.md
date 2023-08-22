SMB Map is a tool that we can use to perform RCE tasks such as connect, enum, upload files or download files by some authentication. 

## How to connect ?

- Shows 
```
smbmap -u guest -p "" -d . -H <Target IP>
```
`-d` = Directory 
