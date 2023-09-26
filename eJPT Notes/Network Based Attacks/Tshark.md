
**`Tshark`** is a command line tool created by the `Wireshark` team and shares the same powerful parsing engine as `Wireshark`. It is capable of doing most things we've come to love `Wireshark` for, but with the "from command line" advantage. This makes it ideal for batch analysis, offline processing and routine automation of traffic analysis tasks.

- `Tshark` is used more for target analysis, we can use it to pull any specific information out instead of going through everything like we were doing in `WireShark`. Its more in-depth, targeted and faster. 

- We can look at the `Tshark` version info using `tshark -v` and the help menu using `tshark -h`. We can pipe the help menu through `more` - `tshark -h | more`. This will give us a better view of the long help menu by showing one page at a time.

- To see the list of interfaces on the system we can use `tshark -D`

- We can run a packet capture on a interface using `tshark -i <interface-name>`

- We can display the contents of a `pcap` file using - `tshark -r <capture_file.pcap>`. This will display all the lines of captures at once which can overwhelm us.  

- To check the protocol hierarchy, we can use command-
```
tshark -r <pcap-file> -z io,phs -q
```

- Apply filter in `tshark` - `tshark -r <pcap-file> -Y "http"`

- Filter to check traffic between 2 IP addresses in a `pcap` file 
```
tshark -r <pcap-file> -Y 'ip.src==<ip-source> && ip.dst==<ip-destination>'
```

- `tshark` command to filter `http` traffic by request method-
```
tshark -r <pcap-file> -Y 'http.request.method==GET'
```

- Command to specify certain fields in the filter
```
tshark -r <pcap-file> -Y 'http.request.method==GET' -Tfields -e frame.time -e ip.src -e http.request.full_uri
```

- Command to look for a particular string in the `pcap` file.
```
tshark -r <pcap-file> -Y 'http contains <string>'
```

- Command to check which IP addresses contacted a specific website.
```
tshark -r <pcap-file> -Y "http.request.method==GET && http.host==www.website.com" -Tfields -e ip.dest
```

- Command to get the cookies for a specific website contacted by a specific IP.
```
tshark -r HTTP_traffic.pcap -Y 'ip contains website.in && ip.src==<src-ip>' -Tfields -e ip.src -e http.cookie
```

- Command to see what browsers the user was utilising.
```
tshark -r HTTP_traffic.pcap -Y 'ip.src==<source-ip> && http' -Tfields -e http.user_agent
```