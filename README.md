# Clear trash can  
rm -RF /home/pi/.local/share/Trash/files/*  

# pi data backup of user  
mkdir /backup  
chown -R pi:pi /backup  
cd /backup; tar -cvf pi.tar /home/pi  

# Create file /backup/maintenance.sh  
```
#!bin/sh  
rm -RF /home/pi/.local/share/Trash/files/*  
rm -RF /home/pi/*  
cd /; tar -xvf /backup/pi.tar  
```
# Executable /backup/maintenance.sh  
chmod u+x /backup/maintenance.sh  
