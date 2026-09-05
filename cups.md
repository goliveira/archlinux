# CUPS

References:

- <https://wiki.archlinux.org/title/CUPS>

---

Install

```bash
sudo pacman -S --needed cups
```

Enable

```bash
sudo systemctl enable cups.service --now
```

The CUPS server can be administered through the web interface at <http://localhost:631>.

(Optional) Install drivers for EPSON. Download `epson-inkjet-printer-escpr` from AUR

```bash
git clone https://aur.archlinux.org/epson-inkjet-printer-escpr.git
```

Make

```bash
cd epson-inkjet-printer-escpr
makepkg -s
```

Install (replace `<version>`)

```bash
sudo pacman -U epson-inkjet-printer-escpr-<version>-x86_64.pkg.tar.zst
```

---

[Back to index](index.md)
