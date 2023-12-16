
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

![image](https://github.com/B4PHOM3T/eJPT-Notes/assets/89618500/cfb4d6bf-5cd6-478c-9e43-8cb2d00cc432)


### Stealth Scan:
![image](https://github.com/B4PHOM3T/eJPT-Notes/assets/89618500/bf1d408f-b09d-480a-a5ec-74b5589792a1)
*It doesn't complete the connection.

### Service Version Scan:

![image](https://github.com/B4PHOM3T/eJPT-Notes/assets/89618500/9a04d4ca-e624-403d-8609-b36122dfd449)


- `-A` - Aggressive Scan performs, OS enum, service enum, default scripts (NSE) and traceroute.

`-T` - Timing Template switch.
- **paranoid (0)** 👉 for **IDS evasion**.
- **sneaky (1)** 👉 for **IDS evasion**.
- **polite (2)** 👉 **Polite mode** slow down the scan to **use less bandwidth and target machine resources.**
- **normal (3)** 👉 **Normal mode** is the default so “-T3” **actually does nothing**.
- **aggressive (4)** 👉 **Aggressive mode** speed up the scans by making the **assumption** that you are on a **reasonably fast and reliable network.**
- **insane (5)** 👉 **Insane mode** assumes that you’re on an **extraordinarily fast network** or you are **willing to sacrifice accuracy for speed.**

- *A `-sU` (UDP SCAN) can take a lot of time to complete as UDP is a connection-less protocol. One way to solve this is by limiting the number of re-transmissions NMAP performs using the `--max-retries` flag.

- `--open` - Will show only the open ports.

- `--top-ports 25` - Shows the top 25 ports.



