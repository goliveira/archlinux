# Alacritty

References:

- <https://wiki.archlinux.org/title/List_of_applications/Utilities#Terminal_emulators>
- <https://wiki.archlinux.org/title/Alacritty>

---

Note: Install basic fonts as described in [fonts](fonts.md).

Install

```bash
sudo pacman -S --needed alacritty
```

Create a config file

```bash
nano ~/.config/alacritty/alacritty.toml
```

Add

```
[env]
TERM = "xterm-256color"

[font.bold]
family = "Noto Sans Mono"
style = "Bold"

[font.bold_italic]
family = "Noto Sans Mono"
style = "Bold Italic"

[font.italic]
family = "Noto Sans Mono"
style = "Italic"

[font.normal]
family = "Noto Sans Mono"
style = "Regular"

[font]
size = 14.0

[keyboard]
bindings = [
{ key = "F11", action = "ToggleFullscreen" }
]
```

---

[Back to index](index.md)
