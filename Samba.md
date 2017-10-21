# Sources
https://www.raspberrypi.org/magpi/samba-file-server/
https://www.raspberrypi.org/forums/viewtopic.php?t=152886
https://www.theurbanpenguin.com/setting-up-a-samba-server-on-raspberry-pi/

# Creating samba users
sudo smbpasswd -a pi

# conf file

```sudo leafpad /etc/samba/smb.conf ```

[share]
  Comment = Pi shared folder
  Path = /share
  Browseable = yes
  Writeable = Yes
  only guest = no
  create mask = 0777
  directory mask = 0777
  Public = yes
  Guest ok = yes

[shared]
comment = Data share
path = /media/USBHDD1
valid users = pi
read only = no
Browseable = yes
Writeable = Yes
only guest = no
create mask = 0777
directory mask = 0777
Public = yes
Guest ok = no


security = USER
browseable = yes
read only = no
Guest ok = no #default


## restart Samba:

sudo /etc/init.d/samba restart



# NAS/ install HDD
## Sources
https://pimylifeup.com/raspberry-pi-nas/

# Create user
sudo useradd pimylifeup -m -G users
sudo passwd pimylifeup
