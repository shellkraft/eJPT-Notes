### What is SMB ?

- SMB (Server Message Block) is a network file sharing protocol that is used to facilitate the sharing of files and peripherals (printers and serial ports) between computers on a local network (LAN).

- SMB uses port 445 (TCP). However, originally, SMB ran on top of NetBIOS using port 139.

- SAMBA is the open source Linux implementation of SMB, and allows Windows systems to access Linux shares and devices.

- The SMB protocol utilizes two levels of authentication, namely:
	+ User Authentication
	+ Share Authentication

- <u>User authentication</u> - This means that access to shared resources (like files or folders) is controlled based on the user's identity. When a user tries to access a shared resource, they must provide their own username and password. User authentication is more individualised and allows different users to have different levels of access to the same share.

- <u>Share authentication</u> - With share authentication, access to shared resources is controlled based on a shared username and password that is the same for everyone who wants to access that specific shared resource. Share authentication is less individualised and provides the same level of access to all users who have the shared credentials.

### What is PsExec ?

- PsExec is a lightweight telnet-replacement developed by Microsoft that allows you execute processes on remote windows systems using any user’s credentials.

- PsExec authentication is performed via SMB.

- We can use the PsExec utility to authenticate with the target system legitimately and run arbitrary commands or launch a remote command prompt.

- It is very similar to RDP, however, instead of controlling the remote system via GUI commands are sent via CMD.

### How to exploit `SMB` with `PsExec` ?

* In order to utilise PsExec to gain access to a Windows target, we will need to identify  legitimate user accounts and their respective passwords or password hashes. 

- This can be done by leveraging various tools and techniques, however, the most common technique will involve performing an SMB login brute-force attack. 

* We can narrow down our brute-force attack to only include common Windows user accounts like: 
	+ Administrator

- After we have obtained a legitimate user account and password, we can use the credentials to authenticate with the target system via PsExec and execute arbitrary system commands or obtain a reverse shell.