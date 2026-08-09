# LaTeX

References:

- <https://wiki.archlinux.org/title/List_of_applications/Documents#Typesetting_systems>
- <https://wiki.archlinux.org/title/TeX_Live>

---

Install

```bash
sudo pacman -S --needed texlive-latexrecommended
```

(Optional) For auxiliary programs (for example, `pdfjam`), install

```bash
sudo pacman -S --needed texlive-binextra
```

(Optional) For portuguese language support, install

```bash
sudo pacman -S --needed texlive-langportuguese
```

(Optional) For image manipulation, install

```bash
sudo pacman -S --needed imagemagick
```

To change the package install location (it defaults to `~/texmf/`), change the `TEXMFHOME` environment variable (add the following command to you `.bash_profile`):

```bash
export TEXMFHOME="$HOME/.local/texmf"
```

As user, execute

```bash
export TEXMFHOME="$HOME/.local/texmf"
tlmgr init-usertree
```

Install packages

```bash
tlmgr --usermode install \
	import \
	subfiles \
	commath \
	framed \
	pgf \
	makecmds
```

LaTeX packages:

- subfiles
	- import
- commath
- framed
- pgf
- makecmds

---

[Back to index](index.md)
