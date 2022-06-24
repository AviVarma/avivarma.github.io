---
title: How to Format a USB Drive Using the Terminal
date: 2022-06-02 10:00:00
tags:
    - Linux
categories:
- notes
keywords:
    - Linux
    - Formatting
    - bash
---


# Format USB Drive On Terminal
With the command `df` you will get a list of drives currently mounted on the system:

```bash
$df
Filesystem      Size  Used Avail Use% Mounted on  
dev              14G     0   14G   0% /dev  
run              14G  1.8M   14G   1% /run  
/dev/nvme0n1p2  469G   21G  424G   5% /  
tmpfs            14G  5.5M   14G   1% /dev/shm  
tmpfs            14G   11M   14G   1% /tmp  
/dev/nvme0n1p1  300M  288K  300M   1% /boot/efi  
/dev/loop2       65M   65M     0 100% /var/lib/snapd/snap/apple-music-for-linux/38  
/dev/loop0       66M   66M     0 100% /var/lib/snapd/snap/gtk-common-themes/1519  
/dev/loop3      128K  128K     0 100% /var/lib/snapd/snap/bare/5  
/dev/loop1       44M   44M     0 100% /var/lib/snapd/snap/snapd/15177  
/dev/loop5      165M  165M     0 100% /var/lib/snapd/snap/gnome-3-28-1804/161  
/dev/loop4       56M   56M     0 100% /var/lib/snapd/snap/core18/2344  
tmpfs           2.8G   76K  2.8G   1% /run/user/1000  
/dev/sda2       932G   25G  908G   3% /run/media/avarma/New Volume  
/dev/sdb1       3.6G  4.0K  3.6G   1% /run/media/avarma/9757-F5DC
```
- We are interested in the `/dev/sdb1`
	- The **sdb1** name is used for USB drives. But you should double check!
- now un-mount the USB drive so we can modify it's contents with the command:

```bash
sudo umount /dev/sdb1
```
- Now Format the drive to FAT32 format:

```bash
sudo mkfs.vfat /dev/sdb1
```
- For NTFS run the following command:
```bash
sudo mkfs.ntfs /dev/sdb1
```
- For exFAT:
```bash
sudo mkfs.exfat /dev/sdb1
```

- Now verify the health of the USB:

```bash
sudo fsck /dev/sdb1
```

[Original Article](https://phoenixnap.com/kb/linux-format-usb)
