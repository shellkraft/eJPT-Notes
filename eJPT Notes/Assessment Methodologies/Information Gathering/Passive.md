# Things to look for:

1) IP addresses
2) Directories hidden from search engines
3) Names
4) Emails
5) Ph. Numbers
6) Addresses 
7) Web Techs used

# DNS Lookup
```
host website.com
```

`host`  - DNS Lookup Utility
Find IP addr of a website using `host` command - `host pokemon.com`

# Hidden Directories

``robots.txt`` - File to tell search engines which directories to not show publicly. 
It is accessible publicly. 

# Website Indexes 

- ``sitemap.xml`` - helps search engines to index the website properly. 
```
pokemon.com/sitemap.xml
```

# Web Technology Footprint

- Tools:
  1) `whatweb` - Not very neat, but works 
```
  whatweb pokemon.com
```

- Browser Plugins:
1) ``BuiltWith`` 
2) ``Wappalyzer`` 

# Download a website

- Tools:
  1) `HTTrack` - Website copier
  
*Installation:*
```
sudo apt-get install webhttrack
```

# Domain Ownership Lookup

- Tools:
  1) `whois` - Whois lookup
```
  whois pokemon.com
```

# Web Recon with NetCraft

- www.sitereport.netcraft.com

# dnsrecon tool

```
dnsrecon -d pokemon.com
```

# DNSDumpster
```
dnsdumpster.com
```

# WAF Detection

https://github.com/EnableSecurity/wafw00f
Detects firewall and name of firewall.

```
wafw00f pokemon.com
```

To look for all possible WAF instances:
```
wafw00f pokemon.com -a 
```

# Subdomain enum 

Using **sublist3r** for subdomain enum.
```
sublist3r -d pokemon.com
```

IT IS passive recon, as it searches for subdomains in search engines. Although it has a bruteforce option, can be enabled using `-b`, but that'll be considered active.

# Google dorks 
Using Google dorks to find subdomains.
https://www.exploit-db.com/google-hacking-database

```
site:*.ine.com intitle:admin
```

If you want to look for sites with directory listing enabled:
```
intitle:index of
```

**It'll show list of web servers hosting files (pirated movies..etc)**

If you want to look for older ver of a website (similar to waybackmachine)
```
cache:pokemon.com
```

Look for websites that leaked directories with passwords:
```
inurl:auth_user_file.txt
inurl:passwd.txt
```

# TheHarvester tool

Find emails, subdomains, IP addr
```
theHarvester -d pokemon.com 
```
