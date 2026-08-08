# 6 - Verify the boot mode

Previous: [Set console keyboard layout](5-console.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Verify_the_boot_mode>

---

After booting the live environment, execute

```bash
cat /sys/firmware/efi/fw_platform_size
```

If the command returns `64`, then the system is booted in 64-bit x64 UEFI mode.

---

Next: [Partition the disks](7-partition.md)
