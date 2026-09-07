# Zotero

References:

- <https://wiki.archlinux.org/title/List_of_applications/Documents#Bibliographic_reference_managers>
- <https://aur.archlinux.org/packages/zotero-bin>

---

Note: Install base-devel as described in [aur](aur.md).

Download from AUR

```bash
git clone https://aur.archlinux.org/zotero-bin.git
```

Make

```bash
cd zotero-bin
makepkg -s
```

Install (replace `<version>`)

```bash
sudo pacman -U zotero-bin-<version>-x86_64.pkg.tar.zst
```

---

[Back to index](index.md)
