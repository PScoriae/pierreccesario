---
title: "HOWTO: Install Arch Linux"
description: Want to speedrun an Arch install?
summary: Want to speedrun an Arch install?
date: 2024-04-21T18:40:23+08:00
cover:
  image: https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/blog/howto-install-archlinux/archlinux-logo-light.webp
  alt: archlinux logo
tags:
  - howto
  - Linux
---

## Preface

### Aim

This guide is mainly for myself to refer to in case I need to:

- Perform a clean install of my Arch Linux setup on bare metal.
- Relearn how to set up some of my personal configs.

However, I am writing this so that anyone may refer to it should they wish to replicate my configurations 1:1 or simply learn how to implement one of my settings into their own system.
Do note that I cannot guarantee this guide’s compatibility with systems other than mine, though it should work.
Plus, I have a knack for documentation and technical writing.

It's important to note that this guide might not be as user-friendly as my typical guides because there are no screenshots here.
The assumption is that you **already** have some familiarity with how Linux works and have attempted something similar before.
For example, in many cases I will just be listing the commands you need to run in quick succession, without much context on what the terminal displays at that point in time.

**This guide will not hold your hand.**

### Rationale

Arch Linux was chosen due to its adherence to the ‘Keep It Simple, Stupid’ (KISS) principle. I find that this resonates with me since I only want the things I need and nothing else. I get to choose what packages I wish to install with little to nothing imposed on me. Similarly, I also like the DIY aspect of the distribution. This allows the install to keep a minimal footprint not only in install size but also in terms of system resources. As such, Arch Linux proved to be a good choice.

It can be argued that Void Linux or Artix Linux would serve the same purpose. Their main appeal would be the lack of _systemd_ but I frankly do not care about that aspect. In my experience, _systemd_ works fine.

### Content

I will be detailing how to exactly replicate my current configuration using the terminal and GUI tools. As such, some Linux knowledge will be required on your end if you wish to adjust it to your needs. Moreover, I may also explain the rationale behind certain choices I have made, which in turn may better inform you about whether to choose a different path than I have. They will be hidden by default since not everyone needs to know about it, but it is still there should you need it.

Many thanks to Ermanno and his video on [How to install Arch Linux with the systemd-boot bootloader.](https://youtu.be/FFXRFTrZ2Lk)
It will form the basis of this installation guide and has been adapted to fit my needs.
For additional information, consult the fantastic [Arch Wiki install guide.](https://wiki.archlinux.org/title/installation_guide)

## Preinstallation

### Downloads

Download the latest ISO for Arch Linux from here then right-click on it in Nautilus and use the Disk Image Writer to burn it onto the USB stick.

If this is not done from Linux, you need to download a program to burn the ISO to your USB drive. I personally use Rufus but I hear great things about Balena Etcher, which is also available on Linux.

## Arch Installation

Of course, if you already have a base Arch install or you have your own way to install Arch, then you can skip to Post Installation.

### Format blocks

Plug in your USB drive into the PC, boot up the PC and go into the BIOS. Override the boot order and boot from the USB.

Select the default option in the bootloader.

Ctrl + L or clear to clear the terminal.

Ensure the system clock is accurate.

```bash
timedatectl set-ntp true
```

List all attached block devices.

```bash
lsblk
```

fdisk desired drive using /dev/NAME.

```bash
fdisk /dev/sda
```

Consult the help menu with `m` if necessary.

Format as GPT.

```bash
g
```

Create a new 300M EFI partition using default partition numbers.

```bash
n
<enter> (use defaults)
<enter> (use defaults)
+300M
t
1
```

Partition rest of block device as regular Linux filesystem storage.

```bash
n
<enter> (use defaults)
<enter> (use defaults)
<enter> (use defaults)
```

Write changes and verify.

```bash
w
lsblk
```

Make the EFI partition a FAT32 file system and Linux filesystem partition into an ext4 filesystem.

```bash
mkfs.fat -F32 /dev/sda1
mkfs.ext4 /dev/sda2
```

Mount main and EFI partition into live boot USB then verify.

```bash
mount /dev/sda2 /mnt
mkdir /mnt/boot
mount /dev/sda1 /mnt/boot
lsblk
```

### Base Arch Install

Install essential packages.

```bash
pacstrap /mnt base linux linux-firmware vim
```

Generate fstab file using UUID and verify.

```bash
genfstab -U /mnt >> /mnt/etc/fstab
cat /mnt/etc/fstab
```

`chroot` into install.

```bash
arch-chroot /mnt
```

Create a 512M [swapfile](https://wiki.archlinux.org/title/swap) in the root directory.
Seeing as most installs are on SSDs, a swap file was chosen instead of a swap partition since the file can be managed and shuffled around by the SSD throughout the whole partition to evenly wear the SSD.
This is not possible with a swap partition since the file is limited to those block locations, thus wearing down that specific area more.

```bash
dd if=/dev/zero of=/swapfile bs=1M count=512 status=progress
```

Set permissions, format as swap and activate.

```bash
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile
```

Edit fstab configuration to support swapfile.

```bash
vim /etc/fstab
---
...
/swapfile none swap defaults 0 0
```

### Localisation

Set a timezone with symlink.

```bash
ln -sf /usr/share/zoneinfo/<your-zone-here> /etc/localtime
```

Set hardware clock.

```bash
hwclock --systohc
```

Uncomment required locales and generate locale. It’s better to choose the UTF-8 version of the locale than the ISO version.

```bash
vim /etc/locale.gen
---
en_GB.UTF-8 UTF-8
---
locale-gen
```

Add locale to `/etc/locale.conf`.

```bash
vim /etc/locale.conf
---
LANG=en_GB.UTF-8
```

### Host settings

Set hostname.

```bash
echo "myhostname" >> /etc/hostname
```

Edit hosts file.

```bash
vim /etc/hosts
---
127.0.0.1   localhost
::1         localhost
127.0.1.1   myhostname.localdomain myhostname
```

Set root password.

```bash
passwd
```

Install more packages for systemd-boot and other needs.

```bash
pacman -S efibootmgr base-devel networkmanager os-prober mtools dosfstools git intel-ucode
```

### systemd-boot

Install systemd-boot

```bash
bootctl --path=/boot install
```

Configure bootloader settings.

```bash
cd /boot/loader
vim loader.conf
---
default arch-*
```

Configure Arch Linux bootloader entry.

```bash
cd entries
vim arch.conf
---
title Arch Linux
linux /vmlinuz-linux
initrd /intel-ucode.img
initrd /initramfs-linux.img
options root=/dev/sda2 rw
```

### Enable NetworkManager

```bash
systemctl enable NetworkManager
```

### Set Up New User

Add a new user to the wheel group and set a password.

```bash
useradd -mG wheel username
passwd username
```

Set up visudo for the user. Uncomment the appropriate user privilege specification under root ALL=(ALL) ALL by entering:

```bash
EDITOR=vim visudo
```

Exit chroot, unmount install and reboot into the new Arch install.

```bash
exit
umount -a
reboot
```

## End

That's it. You've installed Arch Linux.

Albeit, there's pretty much nothing here. It's barebones.

But that's it.
