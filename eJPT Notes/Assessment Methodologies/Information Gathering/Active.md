## DNS Zone Transfer

- Performing zone transfer with ``dnsenum`` 
```
dnsenum pokemon.com
```

- Performing zone transfer with ``dig``
```
dig axfr @nsztm1.digi.ninja zonetransfer.me
```

``axfr`` - Switch for zone transfer
``nsztm1.digi.ninja`` - The nameserver

- Performing zone transfer with ``fierce``
```
fierce -dns pokemon.com
```


##### DNS zone transfer won't work on websites that do not allow it. 
- Websites secured by a firewall might not allow it.

## Netdiscover

Uses ARP requests to discover devices in the network. Shows IP, MAC addr, MAC vendor. 
```
sudo netdiscover -i eth0 -r 192.168.2.0/24
```

### NMAP

- Windows blocks ICMP Ping probes. That's why we use the ``-Pn`` switch. Tells nmap - 'Do not check if the host is online, just perform the scan.'
```
nmap -Pn 10.4.19.214
```

- By default 1000 ports will be scanned. Use ``-F`` switch to turn on fast scan and scan only 100 ports.

**Run nmap script scan to obtain more info about a port.**
