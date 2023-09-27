
### What's IEEE 802.11 protocol ?

The IEEE 802.11 protocol refers to a set of standards for implementing wireless local area networking (WLAN) communication in the 2.4 GHz and 5 GHz frequency bands. It is commonly known as Wi-Fi. 

### For detailed explanation, refer to:
https://tbhaxor.com/wifi-traffic-analysis-in-wireshark/

### WireShark filter to check SSID 

```
wlan.fc.type == 0x0 && wlan.fc.type_subtype == 0x8 && wlan.fixed.capabilities.privacy == 0
```

- The SSID information will be in the drop down menu 
  ``IEEE 802.11 wireless LAN > Tagged Parameters``

### WireShark filter to check in which channel a SSID is operating.

```
wlan.ssid == "<SSID>"
```

- Wi-Fi channel is like a separate lane in the air for wireless devices to communicate without crashing into each other. Picking the right channel can help your Wi-Fi work better by avoiding traffic jams or interference from other Wi-Fi networks.
- This information is linked with frequency and physical medium, therefore you can find it in the **Radio Information** section. `802.11 radio information`

### Filter to check security mechanism in use 

```
wlan contains "<SSID>"
```

- Security mechanisms, such as WPA2-PSK, WEP & "Open," are methods used to protect Wi-Fi networks from unauthorized access and ensure that data transmitted over the network remains confidential.
- We can find the information under the dropdown - 
  ``Tag: RSN Information > Group Cipher Suite``

### Filter to check if WPS is enabled or not 

```
wlan.ssid contains <SSID> && wlan.wfa.ie.type == 0x4
```

- WPS stands for "Wi-Fi Protected Setup," and it's a feature designed to make it easier to connect devices to a secured Wi-Fi network without needing to manually enter a long WiFi password.
- This information can be found under the dropdown `Tag: Vendor Specific`

### Filter to count total number of transmitted & received packets

```
wlan.ta == e8:de:27:16:87:18 || wlan.ra == e8:de:27:16:87:18
```

- ``wlan.ta`` - MAC of the transmitter 
- ``wlan.ra`` - MAC of the receiver.
- The information will be shown at the bottom. 

### `tshark` command to find the MAC address of the device which exchanged data packets with a particular SSID

```
tshark -r <pcap-file> -Y '(wlan.ssid == "<SSID>")' -T fields -e wlan.bssid | sort | uniq
```

The enter this command in `WireShark`
```
wlan.fc.type_subtype == 0x20 && wlan.ra == <mac-we-found>
```

### Filter to find TSF Timestamp

```
wlan.ta == <transmitter-mac> && wlan.ra == <receiver-mac> && wlan.fc.type_subtype == 0x1
```

- TSF stands for "Time Synchronization Function Timestamp." It is a term commonly used in wireless networking, especially in Wi-Fi, to refer to a timestamp value (In Microseconds) used for time synchronization purposes within a wireless network.
- This synchronization ensures that different devices can coordinate their communications effectively without causing interference or collisions.