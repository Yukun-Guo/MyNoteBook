# Linux System Configs

## Change to root user

```bash
sudo su
```

## Add new user with create home directory and set password

```bash
sudo useradd -m -s /bin/bash <username>
sudo passwd <username>
```

## list all groups

```bash
cat /etc/group
```

## Add user to stu group

```bash
sudo usermod -aG stu <username>
```

## Change user

```bash
su - <username>
```

## Change user password

```bash
passwd
```

## List all disks

```bash
lsblk
```

## Mount a disk

### List all partitions of all disks

```bash
sudo fdisk -l
```

### Make directory to mount disk

```bash
sudo mkdir /home/<username>/<diskX_yT>
```

### Mount disk and set permissions

```bash
sudo mount /dev/<sdf2> /home/<username>/<diskX_yT>
sudo chown -R <username>:<username> /home/<username>/<diskX_yT>
sudo chmod -R 755 /home/<username>/<diskX_yT>
```

### Unmount disk

```bash
sudo umount /dev/<sdf2>
```

### Add new disk
    
```bash
# List all disks
lsblk
# Create partition
sudo parted /dev/sdX
# Type: mklabel gpt
# Type: mkpart primary 0% 100%
# Type: quit
# Format partition
sudo mkfs.ext4 /dev/sdXy
# Mount disk
sudo mount /dev/sdXy /home/<username>/<diskX_yT>
# Set permissions
sudo chown -R <username>:<username> /home/<username>/<diskX_yT>
sudo chmod -R 755 /home/<username>/<diskX_yT>
```

## Reconnect Internet

```bash
sudo systemctl restart network-manager # or
sudo ifconfig <interface> up # example: sudo ifconfig eno2 up
```

## create shared folders on Ubuntu for Windows users

```bash
sudo apt-get install samba
sudo mkdir /home/<username>/shared
sudo chmod 777 /home/<username>/shared
sudo nano /etc/samba/smb.conf
```

### Add following lines to the end of the file

```bash
[shared]
path = /home/<username>/shared
available = yes
valid users = <username>
read only = no
browsable = yes
public = yes
writable = yes
```

### Restart samba service

```bash
sudo service smbd restart

sudo ifconfig eno2 up

```

### Access shared folders on Windows, set map network drive

```bash
\\<ip-address>\shared
``````
