# 20 - Boot loader

Previous: [Localhost resolution](19-hosts.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Boot_loader>
- <https://wiki.archlinux.org/title/Boot_loader>
- <https://wiki.archlinux.org/title/Limine>
- <https://wiki.archlinux.org/title/Dm-crypt/Encrypting_an_entire_system#Configuring_the_boot_loader>

---

## EFI boot mode

Install

```bash
pacman -S limine
```

Deploying Limine on UEFI systems involves copying the file `/usr/share/limine/BOOTX64.EFI` to the EFI system partition, and to make the UEFI BIOS aware of it:

```bash
mkdir -p /boot/EFI/limine
cp /usr/share/limine/BOOTX64.EFI /boot/EFI/limine/
```

Limine does not add an entry for the boot loader in the NVRAM automatically. Use `efibootmgr` to setup an entry for Limine:

- <https://wiki.archlinux.org/title/Efibootmgr>

Install

```bash
pacman -S efibootmgr
```

Create an entry (replace `/dev/sda` accordingly):

```bash
efibootmgr --create --disk /dev/sda --part 1 --label "Arch Linux Limine Bootloader" --loader '\EFI\limine\BOOTX64.EFI' --unicode
```

Execute

```bash
nano /boot/EFI/limine/limine.conf
```

Add (replace `/dev/sda2` accordingly)

```
timeout: 10

/Arch Linux (linux)
    protocol: linux
    path: boot():/vmlinuz-linux
    cmdline: cryptdevice=/dev/sda2:root root=/dev/mapper/root rootflags=subvol=@ rw rootfstype=btrfs
    module_path: boot():/initramfs-linux.img
```

---

Next: [Configure swap](21-swap.md)
