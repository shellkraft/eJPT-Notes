### Server Message Block (SMB)

Windows implementation of a file share. Used for sharing access to files, printers, serial ports, and data on a network.

Port number - 139 and 445

*Netbios used to exist in older Windows versions. Used to setup session for SMB.*

# Command to setup SMB

### For connecting:
```
net use Z: \\<Machine IP>\C$ <SMB_PASSWORD> /user:<USERNAME>
```

- `C$` - Drive to host
### For disconnecting:
```
net use * /delete
```

## Connecting SMB using file explorer and CMD:
https://assets.ine.com/labs/ad-manuals/walkthrough-2220.pdf

