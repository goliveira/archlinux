# 21 - Swap

Previous: [Install bootloader](20-bootloader.md)

References:

- <https://wiki.archlinux.org/title/Swap>
- <https://wiki.archlinux.org/title/Zswap#Toggling_zswap>
- <https://wiki.archlinux.org/title/Zram#Usage_as_swap>
- <https://wiki.archlinux.org/title/Zram#Using_zram-generator>

---

Let us configure swap in ram with zram.

First, disable zswap by setting a kernel parameter. Execute

```bash
nano /boot/EFI/limine/limine.conf
```

Add the `zswap.enabled=0` to the list of kernel parameters:

```
timeout: 10

/Arch Linux (linux)
    protocol: linux
    path: boot():/vmlinuz-linux
    cmdline: cryptdevice=/dev/sda2:root root=/dev/mapper/root zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs
    module_path: boot():/initramfs-linux.img
```

Install

```bash
pacman -S zram-generator
```

Create a config file:

```bash
nano /etc/systemd/zram-generator.conf
```

Add

```
[zram0]
```

The unit `systemd-zram-setup@zram0.service` will be automatically loaded.

After reboot, check status with

```bash
systemctl status systemd-zram-setup@zram0.service
```

or

```bash
zramctl
```

or

```bash
swapon --show
```

---

Next: [Configure initramfs](22-initramfs.md)
