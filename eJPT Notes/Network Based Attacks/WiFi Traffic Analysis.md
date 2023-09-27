
### What's IEEE 802.11 protocol ?

The IEEE 802.11 protocol refers to a set of standards for implementing wireless local area networking (WLAN) communication in the 2.4 GHz and 5 GHz frequency bands. It is commonly known as Wi-Fi. 

### How to find a Open (No Security) SSID in the packet dump?

```
(wlan fc.type_subtype== 0x0008) && !(wlan.wfa.ie.wpa.version == 1) && (wlan.tag.number ==48)
```

### How to find a particular SSID ?

```
wlan contains <SSID>
```

### How to know the security mechanism config ?

Example of security mechanisms - WPA-PSK/WPA2-PSK/OPEN etc.

- 