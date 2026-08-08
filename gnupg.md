# GnuPG

References:

- <https://wiki.archlinux.org/title/List_of_applications/Security#Encryption,_signing,_steganography>
- <https://wiki.archlinux.org/title/GnuPG>

---

Installed by default

```bash
sudo pacman -S --needed gnupg
```

Config directory

```
~/.gnupg/
```

Import key (replace `gpg_key.asc`)

```bash
gpg --import gpg_key.asc
```

List public keys (or `-k`)

```bash
gpg --list-public-keys
```

List secret keys (or `-K`)

```bash
gpg --list-secret-keys
```

Edit key (replace `user-id`)

```bash
gpg --edit-key user-id
```

Set trust level to 5:

```
gpg> trust
gpg> 5
gpg> quit
```

---

[Back to index](index.md)
