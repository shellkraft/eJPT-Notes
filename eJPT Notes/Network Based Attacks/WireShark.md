
### Networking Services

+ ARP
+ DHCP
+ SMB
+ FTP
+ Telnet
+ SSH

### What is `MITM`

A man-in-the-middle (MiTM) attack is **a type of cyber attack in which the attacker secretly intercepts and relays messages between two parties who believe they are communicating directly with each other**.

### How to use `WireShark` ?

1. Run a basic `nmap` scan on the subnet.
```
nmap 192.168.1.0/24 -sn
```
- We are using `-sn` switch (Network Mapper) to find the other hosts in the network.

2. Perform an aggressive scan on the discovered hosts.
```
nmap 192.168.1.1-4 -A
```
- In our case, we've discovered 4 hosts on the network.
- One of our hosts have `http` and `https` web servers running. We'll open the web-page in our browser. 

3. We'll now use `Wireshark` to listen on the network interface `eth1`. Select `eth1` and click the fin icon on the top left to start capturing traffic.

4. We can now refresh the web-page to create some network traffic. Stop the capture once its done.

### Understanding `WireShark` settings

- We can save the capture by going to file > save as, this will save the capture in a `PCAPNG` (**`PCAP` Next Generation**) file format. We can then open the `pcapng` file by going to `file > open`. 

- We can go to `View > Name Resolution` and enable `Resolve Network Addresses` for the network addresses to be resolved and displayed to us. Similarly we can also enable `Resolve Physical Addresses` and `Resolve Transport Addresses`.

- We can go to `Capture > Options` to change which interface we want to use or to change output format from `pcapng` to `pcap`

- To see what kind of packets are in the capture, we can go to `Statistics > Protocol Hierchy`.

- We can go to `Statistics > Conversations` to see which machine talked to which machine during the capture.

- Go to `Statistics > Endpoints` to break down by addresses each machine found in the packet capture.

- In the `Time` column, we can check at what time the interaction with a particular packet happened. The default time format in WireShark is relative time in seconds. We can change the format in which time is being displayed by going to `View > Time Display Format`.

- We can also modify other columns by right-clicking on them and clicking `Column Preferences`. We can create our own column and also re-order them.

- We can right-click on a GET/HTTP request and go to `Follow > HTTP Stream`. This will enable  us to see the packet data in Raw (Base64), ASCII, Hexadecimal and other formats.

- Right click on the display filter field and click `Display Filter Expressions`, this will show us thousands of display filters which will help us to filter by any sort of network traffic.

- To go back to the display filter we had set before, we can select the display filter we want from the dropdown history.

- We can go to `File > Export Objects > HTTP`. This will show us all the HTTP objects such as images. 