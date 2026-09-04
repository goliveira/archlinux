# SSH

References:

- <https://wiki.archlinux.org/title/List_of_applications/Security#Encryption,_signing,_steganography>
- <https://wiki.archlinux.org/title/OpenSSH>
- <https://en.wikibooks.org/wiki/OpenSSH>

---

Install

```bash
sudo pacman -S --needed openssh
```

Enable

```bash
sudo systemctl enable sshd.service --now
```

Check status

```bash
systemctl status sshd.service
```

Client config files

```
~/.ssh/config
~/.ssh/authorized_keys
```

Client keys

```
~/.ssh/id_rsa
~/.ssh/id_rsa.pub
```

(Optional) Restore your ssh files from a backup directory:

```bash
DOTFILES = path_to_backup_dir
mkdir ~/.ssh
cp -a $DOTFILES/.ssh/authorized_keys ~/.ssh
cp -a $DOTFILES/.ssh/config ~/.ssh
cp -a $DOTFILES/.ssh/id_rsa ~/.ssh
cp -a $DOTFILES/.ssh/id_rsa.pub ~/.ssh
```

Set default permissions

```bash
chmod 700 ~/.ssh/
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/authorized_keys
chmod 644 ~/.ssh/config
chmod 644 ~/.ssh/id_rsa.pub
```

Accessories:

- SSH agent --- [ssh-agent](ssh-agent.md)

---

[Back to index](index.md)
