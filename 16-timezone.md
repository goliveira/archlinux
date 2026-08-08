# 16 - Timezone

Previous: [Change root](15-chroot.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Time>

---

Create the link `/etc/localtime` by running

```bash
TIMEZONE="America/Sao_Paulo"
ln -sf /usr/share/zoneinfo/$TIMEZONE /etc/localtime
```

Execute

```bash
hwclock --systohc
```

---

Next: [Set localization](17-localization.md)
