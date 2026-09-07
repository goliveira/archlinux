# 28 - Graphical environment

Previous: [Network configuration](27-network.md)

References:

- <https://wiki.archlinux.org/title/General_recommendations#Graphical_user_interface>

---

Let us replace the console terminal by a nice graphical terminal.

Install a desktop environment:

- <https://wiki.archlinux.org/title/Desktop_environment>
- <https://wiki.archlinux.org/title/KDE>

For example, install KDE (minimal):

```bash
sudo pacman -S plasma-desktop
```

In the installation dialog, select options 2) and 1):

```
resolving dependencies...
:: There are 2 providers available for jack:
:: Repository extra
   1) jack2  2) pipewire-jack

Enter a number (default=1): 2

:: There are 2 providers available for qt6-multimedia-backend:
:: Repository extra
   1) qt6-multimedia-ffmpeg  2) qt6-multimedia-gstreamer

Enter a number (default=1): 1
```

Install discover for managing applications and plasma addons:

```bash
sudo pacman -S discover
```

(With NetworkManager only) Install the plasma applet for managing network connections:

```bash
sudo pacman -S plasma-nm
```

Install the plasma applet for audio volume management using pulseaudio:

```bash
sudo pacman -S plasma-pa
```

Install kscreen for monitor support:

```bash
sudo pacman -S kscreen
```

Enter the number 30 to select the english language (or choose another language):

```
Enter a number (default=1): 30
```

Install KDE screenshot capture utility:

```bash
sudo pacman -S spectacle
```

Install a graphical terminal:

```bash
sudo pacman -S konsole
```

Install a file manager:

```bash
sudo pacman -S dolphin
```

Install a text editor:

```bash
sudo pacman -S kate
```

Install a PDF viewer:

```bash
sudo pacman -S okular
```

Install an image viewer:

```bash
sudo pacman -S gwenview
```

Install a display manager:

```bash
sudo pacman -S plasma-login-manager
```

Enable

```bash
sudo systemctl enable plasmalogin.service
```

Reboot the system. A graphical login screen will appear. Enter your username and password. Hit the `super` key and type `konsole`. Now you have a nice graphical terminal.

---

Next: [Install firefox](29-browser.md)
