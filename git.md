# Git

References:

- <https://wiki.archlinux.org/title/List_of_applications/Utilities#Version_control_systems>
- <https://wiki.archlinux.org/title/Git>

---

Install

```bash
sudo pacman -S --needed git
```

Create a config file with

```bash
nano ~/.gitconfig
```

Add

```
[user]
    name = Your name
    email = your_email@gmail.com
[github]
    user = your_username
[color]
    ui = true
[alias]
    tip = log -1 HEAD
```

---

[Back to index](index.md)
