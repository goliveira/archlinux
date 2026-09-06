# 17 - Localization

Previous: [Set timezone](16-timezone.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Localization>

---

Edit `locale.gen` :

```bash
nano /etc/locale.gen
```

Replace the line `#en_US.UTF-8` by 

```
en_US.UTF-8
```

Run

```bash
locale-gen
```

Create `/etc/locale.conf` by running

```bash
echo "LANG=en_US.UTF-8" >> /etc/locale.conf
```

Check the result:

```bash
cat /etc/locale.conf
```

Create `/etc/vconsole.conf` by running (for US keyboard)

```bash
echo "KEYMAP=us" >> /etc/vconsole.conf
```

Alternative (for a Brazilian keyboard), execute

```bash
echo "KEYMAP=br-abnt2" >> /etc/vconsole.conf
```

Check the result:

```bash
cat /etc/vconsole.conf
```

---

Next: [Set hostname](18-hostname.md)
