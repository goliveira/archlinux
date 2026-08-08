# 18 - Hostname

Previous: [Set localization](17-localization.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Network_configuration>

---

Create `/etc/hostname` by executing (replace `myhostname` accordingly)

```bash
echo "myhostname" >> /etc/hostname
```

Check the result with

```bash
cat /etc/hostname
```

---

Next: [Localhost resolution](19-hosts.md)
