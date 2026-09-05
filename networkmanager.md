# NetworkManager

References:

- <https://wiki.archlinux.org/title/Network_configuration>
- <https://wiki.archlinux.org/title/NetworkManager>

---

Install

```bash
sudo pacman -S --needed networkmanager
```

(Optional) If you are using `networkd` and `iwd` to connect to the network, first disable them with

```bash
sudo systemctl disable iwd.service
sudo systemctl disable systemd-networkd.service
```

(You may want to stop the services, but it doesn't seem necessary.)

Enable

```bash
sudo systemctl enable NetworkManager.service --now
```

On a terminal, configure the connection with `nmcli`:

- <https://wiki.archlinux.org/title/NetworkManager#Usage>

List nearby Wi-Fi networks:

```bash
nmcli device wifi list
```

Connect to a Wi-Fi network:

```bash
nmcli device wifi connect SSID_or_BSSID password password
```

Get a list of connections with their names, UUIDs, types and backing devices:

```bash
nmcli connection show
```

(Optional) To provide integration with a desktop environment, install an applet.

For KDE plasma:

```bash
sudo pacman -S --needed plasma-nm
```

For other desktops:

```bash
sudo pacman -S --needed network-manager-applet
```

---

[Back to index](index.md)
