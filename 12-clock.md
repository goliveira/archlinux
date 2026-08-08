# 12 - Update the system clock

Previous: [Connect to the network](11-connect.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Update_the_system_clock>

---

Check the system clock:

```bash
timedatectl status
```

The relevant output line is the following:

```
System clock synchronized: yes
```

If the command above returns `no`, then execute

```bash
systemctl restart systemd-networkd.service
```

This should fix the problem and synchronize the clock. Check the system clock again. The status should be `yes`.

---

Next: [Install essential packages](13-install.md)
