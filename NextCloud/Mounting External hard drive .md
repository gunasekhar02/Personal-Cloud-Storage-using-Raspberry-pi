## Use the following commands in Raspberry pi terminal

### create a mount point
cd /media
sudo mkdir pstorage

### show all uid's
cut -d: -f1,3 /etc/passwd

### show all gid's
getent group

sudo blkid

sudo nano /etc/fstab

UUID=908D-CDD4 /media/pstorage auto defaults,uid=33,gid=33 0 2

sudo mount -a

reboot

### Log back in and type the following to check if drive is mounted

df -h

### Open nextcloud in browser


## Enable external storage

Add mount point to external storage.
/media/pstorage