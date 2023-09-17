### What is SMB ?

- SMB (Server Message Block) is a network file sharing protocol that is used to facilitate the sharing of files and peripherals (printers and serial ports) between computers on a local network (LAN).

- SMB uses port 445 (TCP). However, originally, SMB ran on top of NetBIOS using port 139.

- SAMBA is the open source Linux implementation of SMB, and allows Windows systems to access Linux shares and devices.

- The SMB protocol utilizes two levels of authentication, namely:
	+ User Authentication
	+ Share Authentication

- <u>User authentication</u> - This means that access to shared resources (like files or folders) is controlled based on the user's identity. When a user tries to access a shared resource, they must provide their own username and password. User authentication is more individualised and allows different users to have different levels of access to the same share.

- <u>Share authentication</u> - With share authentication, access to shared resources is controlled based on a shared username and password that is the same for everyone who wants to access that specific shared resource. Share authentication is less individualised and provides the same level of access to all users who have the shared credentials.

