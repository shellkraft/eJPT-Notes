# DNS Records

A - Resolves a hostname or domain to an IPv4 address.
AAAA - Resolves a hostname or domain to an IPv6 address.
NS - Reference to the domains nameserver.
MX - Resolves a domain to a mail server.
CNAME - Used for domain aliases.
TXT - Text record.
HINFO - Host information.
SOA - Domain authority.
SRV - Service records.
PTR - Resolves an IP address to a hostname

- **DNS Zone Files** - Files that contain DNS records.

# Get Network info

- ### ``ifconfig`` alternative.

 You can use ``ip`` command of the ``iproute2`` suite instead of ``ifconfig`` to retrieve network info.
```
ip a s
```
- Stands for IP addr show.
- It provides a wider range of functionalities and is considered more powerful than ``ifconfig``.

# Find hosts [[Network Mapping]]

- If `ping` is unable to find hosts, using arp-scan might help.