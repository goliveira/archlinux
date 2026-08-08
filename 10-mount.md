# 10 - Mount the partitions

Previous: [Format the partitions](9-format.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Mount_the_file_systems>

---

Mount the root volume to `/opt`:

```bash
mount -o compress=zstd:3 /dev/mapper/root /opt
```

Create sub volumes:

```bash
btrfs subvolume create /opt/@
btrfs subvolume create /opt/@home
btrfs subvolume create /opt/@log
btrfs subvolume create /opt/@pkg
```

List sub volumes:

```bash
btrfs subvolume list /opt -t
```

Mount sub volumes to `/mnt`:

```bash
mount -o compress=zstd:3,subvol=@ /dev/mapper/root /mnt
mount --mkdir -o compress=zstd:3,subvol=@home /dev/mapper/root /mnt/home
mount --mkdir -o compress=zstd:3,subvol=@log /dev/mapper/root /mnt/var/log
mount --mkdir -o compress=zstd:3,subvol=@pkg /dev/mapper/root /mnt/var/cache/pacman/pkg
```

For UEFI systems, mount the EFI system partition (replace `/dev/sda1` accordingly):

```bash
mount --mkdir /dev/sda1 /mnt/boot
```

Check with

```bash
lsblk -f
```

---

Next: [Connect to the network](11-connect.md)
