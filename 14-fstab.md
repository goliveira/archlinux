# 14 - Generate fstab

Previous: [Install essential packages](13-install.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Fstab>

---

Execute

```bash
genfstab -U /mnt >> /mnt/etc/fstab
```

Check the result

```bash
cat /mnt/etc/fstab
```

---

Next: [Change root](15-chroot.md)
