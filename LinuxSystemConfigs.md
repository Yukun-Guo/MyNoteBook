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

## Add user to sudo group

```bash
sudo usermod -aG sudo <username>
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

## Reconnect Internet

```bash
sudo systemctl restart network-manager # or
sudo ifconfig <interface> up # example: sudo ifconfig eno2 up
```
