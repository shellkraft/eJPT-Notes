
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

```
tshark -r <pcap> -Y 'wlan.fc.type_subtype==8' -Tfield -e wlan.ssid -e wlan.bssid
```

- Beacon frame is like a periodic signal sent by a Wi-Fi router to announce its presence, share network details, and help devices find and connect to the network.

### Command to find BSSID of a SSID ?

```
tshark -r <pcap> -Y 'wlan.ssid==<SSID>' -Tfields -e wlan.bssid
```

- **SSID** - The SSID is the human-readable name of a Wi-Fi network. It's the name you see when you scan for available Wi-Fi networks on your device.
- **BSSID** - The BSSID is a unique identifier for an individual wireless access point within a Wi-Fi network. It's a hardware-specific identifier for a particular Wi-Fi router or access point.

### Command to find the channel of a SSID 

```
tshark -r <pcap> -Y 'wlan.ssid==<SSID>' -Tfields -e wlan_radio.channel
```

### Find MAC of devices that received de-auth messages

```
tshark -r <pcap> -Y 'wlan.fc.type_subtype==0x000c' -Tfields -e wlan.ra 
```

### Find user agent of a particular MAC address

```
tshark -r <pcap> -Y 'wlan.ta==<SSID> && http' -Tfields -e http.user_agent
```
