# Hunspell

References:

- <https://wiki.archlinux.org/title/Language_checking>
- <https://hunspell.github.io/>

---

Install spell checker

```bash
sudo pacman -S --needed hunspell
```

Install English dictionaries

```bash
sudo pacman -S --needed hunspell-en_us
```

Download Brazilian dictionary from AUR

```bash
git clone https://aur.archlinux.org/hunspell-pt-br.git
```

Make

```bash
cd hunspell-pt-br
makepkg -s
```

Install (replace `<version>`)

```bash
sudo pacman -U hunspell-pt-br-<version>-x86_64.pkg.tar.zst
```

---

[Back to index](index.md)
