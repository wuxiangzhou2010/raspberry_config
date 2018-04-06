## Pi configuration

### default account 
account:`pi`
passwd:	`raspberry`

### raspberryPi source list
change to faster mirror
``` bash
sudo vi  /etc/apt/sources.list
# tsinghua university mirror
deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ jessie main non-free contrib
deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ jessie main non-free contrib

sudo apt-get upgrade
```
### add new user account along with home directory, shell etc.
``` bash
useradd -m -s /bin/bash -d/home/USER_NAME USER_NAME
# add sudo privilege
sudo usermod -a -G sudo USER_NAME
passwd USER_NAME
```

### start/stop/restart network service
``` bash
sudo /etc/init.d/networking restart
sudo service networking restart
# for systemd based 
sudo systemctl start/stop/restart networking
```

### enable ipv4_forward
```
sudo sysctl -w net.ipv4.ip_forward=1
sudo echo 1 > /proc/sys/net/ipv4/ip_forward
sudo edit /etc/sysctl.conf
```

### module, to test usb and others
``` bash
lsusb
lsmod
iwconfig
```

### use dd rather than Win32DiskImager to flash image
previously I was using windwows Win32DiskImager and  SDFormatter, but it's not working properly these days with file not found error every time.then I tried linux dd command, it's working fine
``` bash
# list all disks
sudo fdisk -l

# diskpart(remove all partitions, assume using sdx)
sudo fdisk /dev/sdx
	-m for help
	-d delete a partition
	-w write table to disk and exit
	-n add a new partition
	
# flash the image 
dd bs=4M if=2016-11-25-raspbian-jessie.img of=/dev/sdx
```
