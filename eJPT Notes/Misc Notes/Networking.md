### DNS Records

- A - Resolves a hostname or domain to an IPv4 address.
- AAAA - Resolves a hostname or domain to an IPv6 address.
- NS - Reference to the domains nameserver.
- MX - Resolves a domain to a mail server.
- CNAME - Used for domain aliases.
- TXT - Text record.
- HINFO - Host information.
- SOA - Domain authority.
- SRV - Service records.
- PTR - Resolves an IP address to a hostname

- **DNS Zone Files** - Files that contain DNS records.

### Get Network info

- ### ``ifconfig`` alternative.

 You can use ``ip`` command of the ``iproute2`` suite instead of ``ifconfig`` to retrieve network info.
```
ip a s
```
- Stands for IP addr show.
- It provides a wider range of functionalities and is considered more powerful than ``ifconfig``.

# Find hosts 

- If `ping` is unable to find hosts, using `arp-scan` might help.

# Subnets  explained.

- __Subnet Mask__ - A subnet mask is a 32-bit number that divides an IP address into network and host portions. It consists of a combination of binary 1s (network portion) and 0s (host portion). The subnet mask helps routers and devices determine whether a destination IP address is within the same network or requires routing to a different network.

- **CIDR (Classless Inter-Domain Routing):** CIDR notation is a way to represent IP addresses and their associated routing prefix. It consists of the IP address followed by a slash (/) and the subnet prefix length in bits.

The subnet mask 255.255.255.0 in binary is 11111111.11111111.11111111.00000000. Counting the number of consecutive bits set to 1 gives us 24. So, the subnet mask 255.255.255.0 has a prefix length of 24, which means the first 24 bits of the IP address are considered the network portion, and the remaining 8 bits are the host portion.

## Whats a NULL session ?

A [null session](https://www.blumira.com/glossary/null-session/) occurs when you log in to a system with no username or password. NetBIOS null sessions are a vulnerability found in the Common Internet File System (CIFS) or SMB, depending on the operating system.
