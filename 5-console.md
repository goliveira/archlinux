# 5 - Console keyboard layout

Previous: [Boot the live environment](4-boot.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Set_the_console_keyboard_layout_and_font>

---

The default console layout is `us`. Available layouts can be listed with

```bash
localectl list-keymaps
```

To set the keyboard layout, pass its name to `loadkeys`. For example, to set a Brazilian layout, enter

```bash
loadkeys br-abnt2
```

---

Next: [Verify the boot mode](6-mode.md)
