# 22 - Initramfs

Previous: [Configure swap](21-swap.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Initramfs>
- <https://wiki.archlinux.org/title/Dm-crypt/Encrypting_an_entire_system#Configuring_mkinitcpio>

---

Edit the config file with

```
nano /etc/mkinitcpio.conf
```

Set

```
HOOKS=(base udev autodetect microcode modconf kms keyboard keymap encrypt block filesystems fsck)
```

Note: If you are using the btrfs filesystem for the root partition and includes the module `fsck` on `HOOKS`, you will get an error message when you generate the initramfs. This will happen because the utility `fsck.btrfs` does not exist. In this case, you may remove `fsck` from `HOOKS`.

(Intel) Install intel microcode:

```
pacman -S intel-ucode
```

(AMD) Alternatively, install AMD microcode:

```
pacman -S amd-ucode
```

Create the initial ram disk:

```
mkinitcpio -P
```

---

Next: [Set root password](23-root.md)
