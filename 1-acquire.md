# 1 - Acquire an installation image

References:

- <https://wiki.archlinux.org/title/Installation_guide#Acquire_an_installation_image>

---

The first step is downloading the ISO file:

1. Visit the web page <https://archlinux.org/download/>
2. Choose a mirror
3. Download the file `archlinux-x86_64.iso`
4. Download the files `archlinux-x86_64.iso.sig` and `b2sums.txt`

On Linux, we can download the files on the command line using `wget`. Edit the variable `MIRROR` accordingly and execute:

```bash
MIRROR="https://br.mirrors.cicku.me/archlinux/iso/latest"
wget $MIRROR/archlinux-x86_64.iso -O archlinux-x86_64.iso
wget $MIRROR/archlinux-x86_64.iso.sig -O archlinux-x86_64.iso.sig
wget $MIRROR/b2sums.txt -O b2sums.txt
```

The `-O` option is necessary to overwrite older versions of the files if they already exist.

Note: If wget is not installed on your computer, install it or complete the above steps manually (using a web browser).

---

Next: [Verify the ISO file](2-verify.md)
