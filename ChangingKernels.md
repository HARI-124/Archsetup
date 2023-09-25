# This guide will show help to change your kernels in linux distro

### For systemd bootloader

- Update your packages for me its `sudo pacman -Syu`
- Install your preferred kernel for me its `yay -S linux-zen`
- Change directory to `/boot` folder and open in your preferred text editor for me its neovim
- In the loader folder open the entries folder and create  new `.conf` file. I named it as arch.conf
- Now add the following lines to the arch.conf file(newly created conf file)
```conf

title Archlinux (ZEN)
linux /vmlinuz-linux-zen
initrd /intel-ucode.img
initrd /initramfs-linux-zen.img
options root=PARTUUID=c39eed17-8845-4920-8f44-61b9037d34d6 zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs

```
The title section is the title which will be displayed in the bootloader then change the partuuid by adding
a newly generated UUID. Make sure your are able to see the file names as above or add the filenames correctly 
according to your kernel in this case it it linux zen.

### Changing default kernel
  
In the `loader.conf` file add or change default to arch.conf by adding the line `default arch.conf`.
you can set the time out by adding `timeout 5` 
