``` bash
#/etc/network/interfaces

#loopback configuration
auto lo
iface lo inet loopback

#Ethernet configuration, static
auto eth0
allow-hotplug eth0
iface eth0 inet static
address 192.168.1.123
netmask 255.255.255.0
gateway 192.168.1.1

#wifi configuration(hostapd, not working properly for the moment)
auto wlan0
allow-hotplug wlan0
iface wlan0 inet static
hostapd /etc/hostapd/hostapd.conf
address 192.168.8.1
netmask 255.255.255.0
```
