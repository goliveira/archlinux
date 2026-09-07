# LaTeX

References:

- <https://wiki.archlinux.org/title/List_of_applications/Documents#Typesetting_systems>
- <https://wiki.archlinux.org/title/TeX_Live>

---

Install

```bash
sudo pacman -S --needed texlive-latexrecommended
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

## LaTeX packages

- subfiles
	- import
- commath
- framed
- pgf
- makecmds

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

## Accessories

- texlive-binextra
- texlive-langportuguese
- imagemagick

For auxiliary programs (for example, `pdfjam`), install

```bash
sudo pacman -S --needed texlive-binextra
```

For portuguese language support, install

```bash
sudo pacman -S --needed texlive-langportuguese
```

For image manipulation, install

```bash
sudo pacman -S --needed imagemagick
```

---

[Back to index](index.md)
