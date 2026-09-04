# SSH agent (optional)

References:

- <https://wiki.archlinux.org/title/SSH_keys#Start_ssh-agent_with_systemd_user>

---

Note: Install SSH as described in [ssh](ssh.md).

Edit bash config file

```bash
nano ~/.bash_profile
```

Add (at the top of the file)

```
# Set variable for using ssh-agent with systemd service
export SSH_AUTH_SOCK="$XDG_RUNTIME_DIR/ssh-agent.socket"
```

Create a config file

```bash
nano ~/.ssh/config
```

Add

```
AddKeysToAgent yes
```

As user, enable

```bash
systemctl --user enable ssh-agent.socket --now
```

Check status

```bash
systemctl --user status ssh-agent.socket
```

The first time you run ssh, the key will be passed to the agent after you enter the password.

Alternatively, you may pass a key to the agent with

```bash
ssh-add ~/.ssh/id_rsa
```

---

[Back to index](index.md)
