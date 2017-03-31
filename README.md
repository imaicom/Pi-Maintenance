# Clear trash can  
```
rm -Rf /home/pi/.local/share/Trash/files/*
```
# backup of pi user data  
```
sudo su
mkdir /backup
chown pi:pi /backup
cd /backup; tar -cvf pi.tar /home/pi
```
# Create file /backup/restore.sh  
```
vi /backup/restore.sh
i

#!bin/sh
rm -Rf /home/pi/*
cd /; tar -xvf /backup/pi.tar
rm -Rf /home/pi/.local/share/Trash/files/*
[esc][Z][Z]
```
# Execute /backup/restore.sh  
```
chmod u+x /backup/restore.sh
sh /backup/restore.sh
```
