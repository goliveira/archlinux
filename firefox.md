# Firefox

References:

- <https://wiki.archlinux.org/title/Firefox>
- <https://wiki.archlinux.org/title/List_of_applications/Internet#Web_browsers>

---

Install

```bash
sudo pacman -S firefox-i18n-pt-br
```

(Replace `firefox-i18n-pt-br` accordingly to your language or simply install `firefox`.)

In the installation dialog, select option 2) for `pipewire-jack`:

```
resolving dependencies...
:: There are 2 providers available for jack:
:: Repository extra
   1) jack2  2) pipewire-jack

Enter a number (default=1): 2
```

The pipewire sound server will be automatically installed as a dependency (if needed).

Execute

```bash
firefox
```

Sound playback (including unmuting) should work out of the box. To test sound, go to `www.youtube.com` and play some music.

---

[Back to index](index.md)
