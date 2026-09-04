# 19 - Localhost resolution

Previous: [Set hostname](18-hostname.md)

References:

- <https://wiki.archlinux.org/title/Network_configuration#Local_network_hostname_resolution>

---

Edit `/etc/hosts` by running (replace `myhostname` accordingly)

```bash
echo "127.0.1.1        myhostname" >> /etc/hosts
```

Check the result:

```bash
cat /etc/hosts
```

The file should contain the following lines (replace `myhostname` accordingly):

```
127.0.0.1    localhost
::1          localhost
127.0.1.1    myhostname
```

---

Next: [Install bootloader](20-bootloader.md)
