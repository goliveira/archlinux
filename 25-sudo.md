# 25 - Privilege elevation

Previous: [Create a new user](24-user.md)

References:

- <https://wiki.archlinux.org/title/Sudo>

---

Install

```bash
pacman -S sudo
```

Edit `/etc/sudoers`:

```bash
EDITOR=nano visudo
```

Replace the line `# %wheel ALL=(ALL:ALL) ALL` by 

```
%wheel ALL=(ALL:ALL) ALL
```

Users in the group `wheel` can execute commands as root by adding`sudo` to the command.

---

Next: [Reboot the system](26-reboot.md)
