# Pass

References:

- <https://wiki.archlinux.org/title/List_of_applications/Security#Password_managers>
- <https://wiki.archlinux.org/title/Pass>

---

Install

```bash
sudo pacman -S --needed pass
```

Password store directory

```
~/.password-store/
```

Set recommended permission

```bash
chmod 600 ~/.password-store/
```

(Optional) As user, restore you password gpg key from a backup directory (replace `secret_key.asc` accordingly):

```bash
DOTFILES = path_to_password_gpg_keys
gpg --import $DOTFILES/keys/gpg-pass/private_key.asc
```

List secret keys with (or `-K`)

```bash
gpg --list-secret-keys
```

For example, you will get something like

```
[keyboxd]
---------
sec   rsa2048 2014-08-13 [SC]
      XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
uid           [ultimate] Password Storage Key
ssb   rsa2048 2014-08-13 [E]
```

Edit the key with

```bash
gpg --edit-key "Password Storage"
```

Set trust level to 5:

```
gpg> trust
gpg> 5
gpg> quit
```

---

[Back to index](index.md)
