# Lighttpd

References:

- <https://wiki.archlinux.org/title/List_of_applications/Internet#Web_servers>
- <https://wiki.archlinux.org/title/Lighttpd>

---

Install

```bash
sudo pacman -S --needed lighttpd
```

Edit config file

```bash
sudo nano /etc/lighttpd/lighttpd.conf
```

Add

```
server.errorlog = "/var/log/lighttpd/error.log"
mimetype.assign = (  
                       ".html" => "text/html",
                       ".txt" => "text/plain",
                       ".css" => "text/css",
                       ".js" => "application/x-javascript",
                       ".jpg" => "image/jpeg",
                       ".jpeg" => "image/jpeg",
                       ".gif" => "image/gif",
                       ".png" => "image/png",
                       ".pdf" => "application/pdf",
                       "" => "application/octet-stream"
                   )
# Path to user directory relative to ~/
userdir.path = "Projects/myhomepage"
server.modules += ( "mod_userdir" )
```

To access user directory, set

```bash
sudo chmod g+rx,o+rx ~/
```

Enable

```bash
sudo systemctl enable lighttpd.service --now
```

---

[Back to index](index.md)
