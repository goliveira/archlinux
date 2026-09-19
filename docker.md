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

To update an app, run the following command in the directory containing your `docker-compose.yml` file:

```bash
docker compose pull
```

Recreate and start the updated containers in detached mode:

```bash
docker compose up -d
```

Remove obsolete Docker container images to free up disk space:

```
docker image prune
```

## Accessories

- [lazydocker](lazydocker.md) (terminal user interface)

---

[Back to index](index.md)
