# 13 - Install essential packages

Previous: [Update the system clock](12-clock.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Install_essential_packages>

---

Execute

```bash
pacstrap -K /mnt base linux linux-firmware nano bash-completion man-db man-pages texinfo iwd dhcpcd networkmanager
```

Essential packages:

- base (minimal packages for a basic Arch Linux installation)
- linux (the Linux kernel and modules)
- linux-firmare (firmware files for Linux)
- nano (basic text editor)
- bash-completion (completions for the bash shell)
- man-db, man-pages (man pages)
- texinfo (info pages)
- iwd (internet wireless daemon)
- dhcpcd (DHCP client)
- networkmanager (networkmanager)

---

Next: [Generate fstab](14-fstab.md)
