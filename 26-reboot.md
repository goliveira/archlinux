# 26 - Reboot

Previous: [Configure privilege elevation](25-sudo.md)

---

Exit chroot environment:

```bash
exit
```

Umount partitions:

```bash
umount -R /mnt
umount /opt
```

(Wireless only) Leave IP address (replace `wlan0` accordingly):

```bash
dhcpcd -k wlan0
```

(Wireless only) Close wifi connection (replace `wlan0` accordingly):

```bash
iwctl
station wlan0 disconnect
quit
```

(Wireless only) Turn off device (replace `wlan0` accordingly):

```bash
ip link set wlan0 down
```

Close LUKS partition:

```bash
cryptsetup close root
```

Reboot the system:

```bash
poweroff
```

Remove the usb drive and boot your new installed system.

---

Next: [Network configuration](27-network.md)
