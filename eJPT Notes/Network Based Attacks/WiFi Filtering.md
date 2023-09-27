
### Filtering De-auth Packets with `tshark`

```
tshark -r <pcap> -Y 'wlan.fc.type_subtype==0x000c'
```

- Deauthentication packets are typically used in situations where there's a need to disconnect a device from a network remotely or when an authorized entity (like a network administrator) needs to terminate a connection for specific reasons, such as security or network management.