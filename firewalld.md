# Firewalld

References:

- <https://wiki.archlinux.org/title/Category:Firewalls>
- <https://wiki.archlinux.org/title/Firewalld>

---

Install

```bash
sudo pacman -S --needed firewalld
```

Enable

```bash
sudo systemctl enable firewalld.service --now
```

Check status

```bash
systemctl status firewalld.service
```

(Optional) Install a graphical user interface

```bash
sudo pacman -S --needed firewall-config
```

Accessories:

- firewall-config --- Graphical user interface

---

[Back to index](index.md)
