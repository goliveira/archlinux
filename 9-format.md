# 9 - Format the partitions

Previous: [Erase the partition](8-erase.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Format_the_partitions>

---

Format the EFI system partition and label it (replace `/dev/sda1` accordingly):

```bash
mkfs.fat -F 32 /dev/sda1
fatlabel /dev/sda1 EFI
```

Format the LUKS partition and label it (replace `/dev/sda2` accordingly):

```bash
cryptsetup luksFormat /dev/sda2
cryptsetup config /dev/sda2 --label "LUKS"
```

Check the results:

```bash
cryptsetup luksDump /dev/sda2
lsblk -f
```

Open the LUKS partition:

```bash
cryptsetup open /dev/sda2 root
```

Format and label the mapper device:

```bash
mkfs.btrfs -L LINUX /dev/mapper/root
```

---

Next: [Mount the partitions](10-mount.md)
