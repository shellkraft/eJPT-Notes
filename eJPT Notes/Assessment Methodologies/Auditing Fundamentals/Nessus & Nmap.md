
### How to use Nessus ?

- Nessus Default URL is: https://localhost:8834
- The default URL will take us to the login page.
- We've to enter hostname, Nessus will figure out the IP by performing an discovery scan. 
- The basic scan results will not contain much details.
- We can perform a advanced scan (custom scan) for better analysis. 
- After a scan is done, report can be generated in PDF, HTML or CSV format.

### Using `nmap` for audit

- The organisation we are auditing should have a network map, containing the IP addresses of all the devices connected to the network.
- It is similar to a PenTest, but we aren't performing it in a black box point of view. 

First we'll perform a scan on the subnet. 

```
nmap 192.168.100.0/24
```

*The scan result should provide us with multiple hosts connected to the network and port scan on each of them.*

We can then perform an aggressive scan (A) on individual hosts.

```
nmap 192.168.100.1,2,3,4 -A
```

*The aggressive scan should provide us a more detailed overview, but it'll take a longer time to complete.*