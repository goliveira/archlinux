# 3 - Prepare an installation medium

Previous: [Verify the ISO file](2-verify.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Prepare_an_installation_medium>

---

Find out the name of your USB drive with `lsblk`. Edit the variable `USBDRIVE` accordingly. Make sure that the drive is not mounted. Copy the ISO file to the USB drive using `dd`:

```bash
USBDRIVE="/dev/sdb"
sudo dd bs=4M if=archlinux-x86_64.iso of=$USBDRIVE conv=fsync oflag=direct status=progress
```

Note: Execute the above command in the same directory where you saved the file archlinux-x86_64.iso (or edit the path in the above command).

On Mac OS or Windows, see instructions in

- <https://wiki.archlinux.org/title/USB_flash_installation_medium>.

---

Next: [Boot the live environment](4-boot.md)
