# Syncthing

References:

- <https://wiki.archlinux.org/title/List_of_applications/Utilities#File_synchronization_and_backup>
- <https://wiki.archlinux.org/title/Syncthing>

---

Install

```bash
sudo pacman -S --needed syncthing
```

Enable (replace `username` accordingly)

```bash
sudo systemctl enable syncthing@username.service --now
```

After reboot, to set up syncthing go to the web interface at <http://localhost:8384>.

---

[Back to index](index.md)
