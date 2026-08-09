# Fonts

References:

- <https://wiki.archlinux.org/title/General_recommendations#Fonts>
- <https://wiki.archlinux.org/title/Fonts>

---

(Recommended) Basic fonts:

```bash
sudo pacman -S --needed \
	noto-fonts \
	noto-fonts-cjk \
	noto-fonts-emoji \
	noto-fonts-extra \
	ttf-noto-nerd
```

Fonts for [libreoffice](libreoffice.md):

```bash
sudo pacman -S --needed \
    ttf-caladea \
    ttf-carlito \
    ttf-dejavu \
    ttf-liberation \
    ttf-linux-libertine-g \
    noto-fonts \
    adobe-source-code-pro-fonts \
    adobe-source-sans-fonts \
    adobe-source-serif-fonts
```

Download `ttf-gentium-basic` font from AUR

```bash
git clone https://aur.archlinux.org/ttf-gentium-basic.git
```

Make

```bash
cd ttf-gentium-basic
makepkg -s
```

Install (replace `<version>`)

```bash
sudo pacman -U ttf-gentium-basic-<version>-x86_64.pkg.tar.zst
```

Download `ttf-ms-fonts` font from AUR

```bash
git clone https://aur.archlinux.org/ttf-ms-fonts.git
```

Make

```bash
cd ttf-ms-fonts
makepkg -s
```

Install (replace `<version>`)

```bash
sudo pacman -U ttf-ms-fonts-<version>-x86_64.pkg.tar.zst
```

---

[Back to index](index.md)
