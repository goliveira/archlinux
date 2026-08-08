# 24 - Create a new user

Previous: [Set root password](23-root.md)

References:

- <https://wiki.archlinux.org/index.php/Users_and_groups#User_management>

---

To check user defaults, run

```bash
useradd --defaults
```

To create a new user, execute (replace `username` accordingly):

```bash
useradd -m -G wheel username
```

Set user password (replace `username` accordingly):

```bash
passwd username
```

---

Next: [Configure privilege elevation](25-sudo.md)
