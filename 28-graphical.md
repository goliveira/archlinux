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

In the installation dialog, select option 2) for `pipewire-jack`:

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

The pipewire sound server will be automatically installed as a dependency.

Install discover for managing applications and plasma addons:

```bash
sudo pacman -S discover
```

Install the plasma applet for audio volume management using pulseaudio:

```bash
sudo pacman -S plasma-pa
```

Install KDE screenshot capture utility:

```bash
sudo pacman -S spectacle
```

Install kscreen for multi monitor support:

```bash
sudo pacman -S kscreen
```

Enter the number 30 to select the english language (or choose another language):

```
Enter a number (default=1): 30
```

(With NetworkManager only) Install the plasma applet for managing network connections:

```bash
sudo pacman -S plasma-nm
```

Install a display manager:

- <https://wiki.archlinux.org/title/Display_manager>
- <https://wiki.archlinux.org/title/Plasma_Login_Manager>

For example, install plasma login manager:

```bash
sudo pacman -S plasma-login-manager
```

Enable

```bash
sudo systemctl enable plasmalogin.service
```

Install a graphical terminal:

- <https://wiki.archlinux.org/title/List_of_applications/Utilities#Terminal_emulators>
- <https://wiki.archlinux.org/title/Konsole>

For example, install konsole:

```bash
sudo pacman -S konsole
```

Reboot the system. A graphical login screen will appear. Enter your username and password. Hit the `super` key and type `konsole`. Now you have a nice graphical terminal.

---

Next: [Install firefox](29-browser.md)
