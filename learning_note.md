# Pi configuration

### default acount 
account:`pi`
passwd:`raspberry`

### RaspberryPi source list
change to faster source
```
sudo vi  /etc/apt/sources.list

# tsinghua university mirror
deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ jessie main non-free contrib
deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ jessie main non-free contrib

sudo apt-get upgrade
```

### Change passwd
for ubuntu distribution, root account is not enabled by default
use `sudo passwd` to active and set password for root account
```
sudo passwd
sudo passwd root
```
### add new user account along with home directory,shell etc.
```
useradd -m -s /bin/bash -d/home/USER_NAME USER_NAME
# add sudo privilege
sudo usermod -a -G sudo USER_NAME
passwd USER_NAME
```
### .bashrc to simplify some work
use source ~/.bashrc(or . ~/.bashrc)
```
alias r='rm -rf'
alias u='svn update'
```

### To start/stop/restart network service
```
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
```
lsusb
lsmod
iwconfig
```
