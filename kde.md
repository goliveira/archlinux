# KDE

References:

- <https://wiki.archlinux.org/title/KDE>
- <https://wiki.archlinux.org/title/Desktop_environment>

-----

Install (minimal installation)

```bash
sudo pacman -S --needed plasma-desktop
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

## Accessories

- discover
- kscreen
- plasma-pa
- plasma-nm
- spectacle
- [plasmalogin](plasmalogin.md)
- [konsole](konsole.md)

Install discover for managing applications and plasma addons:

```bash
sudo pacman -S --needed discover
```

Install kscreen for monitor support:

```bash
sudo pacman -S --needed kscreen
```

Enter the number 30 to select the english language (or choose another language):

```
Enter a number (default=1): 30
```

Install the plasma applet for audio volume management using pulseaudio:

```bash
sudo pacman -S --needed plasma-pa
```

(With NetworkManager only) Install the plasma applet for managing network connections:

```bash
sudo pacman -S --needed plasma-nm
```

Install KDE screenshot capture utility:

```bash
sudo pacman -S --needed spectacle
```

---

[Back to index](index.md)
