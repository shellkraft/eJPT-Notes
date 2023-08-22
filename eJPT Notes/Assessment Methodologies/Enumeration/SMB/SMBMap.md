SMB Map is a tool that we can use to perform RCE tasks such as connect, enum, upload files or download files by some authentication. 

## How to connect ?

- Shows disks and permissions:
```
smbmap -u guest -p "" -d . -H <Target IP>
```
`-d` = Directory 

```
smbmap -H <Target IP> -u <username> -p <pass> -x 'ipconfig'
```
`-x` = CMD command to run

### More smbmap switches:

- `-L` - Shows the mapped drives.
- `-r` - Works like `ls` of Linux (`-r 'C$'`). C$ is the C Drive.
- `--upload` - Upload files using SMB  (`--upload '/root/backdoor' 'C$\Backdoor'`)
- `--download` - Download a file
- 