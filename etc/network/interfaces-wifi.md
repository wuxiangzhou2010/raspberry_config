``` bash
#configuration for a wifi use wpa-supplicant
auto lo
iface lo inet lookpack
iface eth0 inet dhcp

allow-hotplug wlan0

#configuration for AP
iface wlan0 inet static
address 192.168.1.123
netmask 255.255.255.0

#configuration for wifi
#iface wlan0 inet manual
#wpa-roam /etc/wpa_supplicant/wpa_supplicant.conf
#iface default inet dhcp
```
