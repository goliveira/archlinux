# Reflector

References:

- <https://wiki.archlinux.org/title/Mirrors#Client-side_ranking>
- <https://wiki.archlinux.org/title/Reflector>

Install

```bash
sudo pacman -S --needed reflector
```

Get help

```bash
man reflector
reflector --help
```

Backup mirrorlist

```bash
cd /etc/pacman.d
sudo cp mirrorlist mirrorlist.backup
```

Sort the five most recently synchronized mirrors by download speed and overwrite the local mirrorlist:

```bash
sudo reflector --latest 5 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```

Check results

```bash
cat /etc/mirrorlist
```

---

[Back to index](index.md)
