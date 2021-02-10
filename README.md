# Termux

```bash
passwd
pkg upgrade
pkg install nano
pkg install htop
```

## SSH

```bash
pkg install openssh
sshd
```

ssh user@172.16.8.32:8022

## mosquitto

```bash
pkg install mosquitto
cd /data/data/com.termux/files/usr/etc/mosquitto
nano mosquitto.conf
```

```python
#default listener
port 1883
protocol mqtt
#extra listener
listener 8883
protocol websockets
mosquitto -d -c mosquitto.conf
#logging
connection_messages false
```

## Issue

### Can't not update because conflict with libandroid-support::arch64 

```bash
rm -rf $PREFIX
```

restart app

reinstall all package

### ping

can not ping without root permission

```bash
#test ip:port
telnet 172.16.8.29 80
nc -vz 172.16.0.130 80
nmap -p 80 172.16.0.130 
nmap -T5 -sP 192.168.1.0-255 #scan alive ip
(echo >/dev/tcp/172.16.0.130/80) &>/dev/null && echo "Open" || echo "Close"
```

