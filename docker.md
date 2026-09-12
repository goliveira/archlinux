# Docker

References:

- <https://wiki.archlinux.org/title/Docker>

---

Install

```bash
sudo pacman -S --needed docker
```

Enable

```bash
sudo systemctl enable docker.service --now
```

Check

```bash
sudo docker info
```

(Optional) Add user to docker groups (replace `<username>` accordingly):

```bash
sudo gpasswd -g docker <username>
```

## Accessories

- [lazydocker](lazydocker.md) (terminal user interface)

---

[Back to index](index.md)
