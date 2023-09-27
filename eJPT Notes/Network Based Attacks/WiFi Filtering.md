
### Filtering De-auth Packets with `tshark`

```
tshark -r <pcap> -Y 'wlan.fc.type_subtype==0x000c'
```

- Deauthentication packets are typically used in situations where there's a need to disconnect a device from a network remotely or when an authorized entity (like a network administrator) needs to terminate a connection for specific reasons, such as security or network management.

### Filtering WPA handshake packets with `tshark`

```
tshark -r <pcap> -Y 'eapol'
```

- `EAPOL` is a protocol used for the exchange of authentication and encryption keys.
- `WPA` handshake establishes a secure connection between the device and the network by confirming that the device has the correct credentials (encryption key) to access the network.

### Command to print the SSID and BSSID of all the Beacon frames
