ARP (Address Resolution Protocol) spoofing, which is a technique used in network attacks. ARP spoofing involves sending fake ARP messages on a local network to associate the attacker's MAC address with the IP address of another host.

### How to ARP spoof ?

1. Scan the subnet to discover hosts that we can target.

2. Enable IP forwarding. By doing this we'll disguise our local machine to act as the network router or gateway.
```
echo 1 > /proc/sys/net/ipv4/ip_forward
```

3. Start the attack.
```
arpspoof -i eth1 -t 10.100.13.37 -r 10.100.13.36
```

- `-i` - Interface to use for the attack.
- `-t` - The IP address to impersonate
- `-r` - Target whose traffic we want to intercept.

### How is it working ?

The attacker is impersonating the IP address 10.100.13.37 by spoofing the MAC address associated with it. By doing this, the attacker is essentially telling the target machine at IP address 10.100.13.36 that if it wants to communicate with 10.100.13.37, it should send network traffic to the attacker's MAC address instead of the legitimate MAC address for 10.100.13.37.

### How to capture sensitive data using this ?

1. Perform the `ARP` spoof with intercept on in `WireShark`.

2. `WireShark` will capture packets that was meant for the IP address we are impersonating which might reveal sensitive data to us if the communication is un-encrypted.

3. In our case, we can see packets sent using `telnet` in the capture.

4. We will now filter the capture to show only `telnet` data.

5. We can now `follow` the `TCP stream` by right clicking on a telnet packet to further analyse the data packets, which can potentially disclose sensitive data.

6. The telnet packet contains telnet login credentials in clear text. We can now use telnet to login into the target machine we were intercepting.  `telnet <ip>`

7. Since credential information (usernames and passwords) submitted through telnet is not encrypted we were able to perform this attack.

