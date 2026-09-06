# Avahi

References:

- <https://wiki.archlinux.org/title/Avahi>

---

Install

```bash
sudo pacman -S --needed avahi
```

Enable

```bash
sudo systemctl enable avahi.service --now
```

Open port 5353/udp if you are using a firewall.

We will keep using systemd-resolved mDNS service.

For NetworkManager, it should work out of the box.

For systemd-networkd, edit systemd-resolved config file:

```bash
sudo nano /etc/systemd/resolved.conf
```

Set

```
MulticastDNS=resolve
```

Set `MulticastDNS=resolve` in the "Network" section of each interface config file.

The Avahi Zeroconf Browser avahi-discover shows the various services on your network. Note that it needs Avahi's optional dependencies gtk3, python-dbus and python-gobject. You can also browse SSH and VNC Servers using bssh and bvnc respectively.

(Optional) Install

```bash
sudo pacman -S --needed gtk3 python-dbus python-gobject
```

---

[Back to index](index.md)
