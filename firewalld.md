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

Find services:

```bash
sudo firewall-cmd --get-services
```

Get information (ports) about a service. For example:

```bash
sudo firewall-cmd --info-service=http
```

Open some ports. For example:

```bash
sudo firewall-cmd --add-service=http
sudo firewall-cmd --add-service=mdns
sudo firewall-cmd --add-service=syncthing
```

Make runtime changes permanent:

```bash
sudo firewall-cmd --runtime-to-permanent
```

Accessories:

- firewall-config --- Graphical user interface

---

[Back to index](index.md)
