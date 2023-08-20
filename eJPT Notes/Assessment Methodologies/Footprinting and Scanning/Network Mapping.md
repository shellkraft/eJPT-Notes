
### Using ARP Scan

ARP - Address Resolution Protocol

**Command:**
```
arp-scan -i tun0 -g 10.0.2.15/24
```

``-i`` = interface
`-g` = generate based of....

**Communication:**
```
Who has 10.10.1.5? Tell 10.10.1.7
10.10.1.5 is at 00:0c:29:af:ea:d2

10.10.1.7 adds findings to ARP table
```

*We can use WireShark to monitor the ARP scan and see the MAC addr in endpoints menu* 

### FPING 

Unlike `ping` command, `fping` can be used to ping multiple hosts at the same time

```
fping -i tun0 -g 10.0.2.15/24 -a
```

`-a` = To check which are alive

### Using NMAP

```
nmap -sn 10.0.2.15/24
```

*We can also use the GUI version of Nmap, Zenmap*

## How do the scans work ?

### TCP Connect Scan:

![[Pasted image 20230818004851.png]]

### Stealth Scan:

![[Pasted image 20230818005259.png]]*It doesn't complete the connection.

### Service Version Scan:

![[Pasted image 20230818005613.png]]

`-A` - Aggressive Scan performs, OS enum, service enum, default scripts (NSE) and traceroute.

`-T` - Timing Template switch. The template names are `paranoid` (`0`), `sneaky` (`1`), `polite` (`2`), `normal` (`3`), `aggressive` (`4`), and `insane` (`5`). The first two are for IDS evasion. Polite mode slows down the scan to use less bandwidth and target machine resources. Normal mode is the default and so `-T3` does nothing. Aggressive mode speeds scans up by making the assumption that you are on a reasonably fast and reliable network. Finally insane mode assumes that you are on an extraordinarily fast network or are willing to sacrifice some accuracy for speed.
