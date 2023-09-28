
+ `Nmap` is a free and open-source network scanner that can be used to discover hosts on a network as well as scan targets for open ports.

+ It can also be used to enumerate the services running on open ports as well as the operating system running on the target system.

+ We can output the results of our `Nmap` scan in to a format that can be imported into `MSF` for vulnerability detection and exploitation.

### Outputting Scan results to a file

**We'll now output the `nmap` scan result into `xml` file to be imported into `MSF`**

```
nmap -Pn -sV -0 <target-ip> -oX <name-of-file>
```
