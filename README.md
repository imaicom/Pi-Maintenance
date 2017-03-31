# [ Clear trash can ]  
rm -RF /home/pi/.local/share/Trash/files/*  

# [ pi Data backup of user ]  
mkdir /backup  
chown -R pi:pi /backup  
cd /backup; tar -cvf pi.tar /home/pi  

# [ /backup/mente.sh Create file ]  
#!bin/sh  
rm -RF /home/pi/.local/share/Trash/files/*  
rm -RF /home/pi/*  
cd /; tar -xvf /backup/pi.tar  
