# Clear trash can  
```
rm -Rf /home/pi/.local/share/Trash/files/*  
```
# pi data backup of user  
```
sudo su
mkdir /backup  
chown pi:pi /backup  
cd /backup; tar -cvf pi.tar /home/pi  
```
# Create file /backup/maintenance.sh  
```
#!bin/sh  
rm -Rf /home/pi/*  
cd /; tar -xvf /backup/pi.tar  
rm -Rf /home/pi/.local/share/Trash/files/*  
```
# Executable /backup/maintenance.sh  
```
chmod u+x /backup/maintenance.sh
sh /backup/maintenance.sh
```
