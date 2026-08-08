# 7 - Partition the disks

Previous: [Verify the boot mode](6-mode.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Partition_the_disks>

---

If you have already partitioned the disks, skip to [8-erase](8-erase.md) or [9-format](9-format.md).

List devices and partitions:

```bash
fdisk -l
```

List partitions and tables in a specific device (replace `/dev/sda` accordingly):

```bash
gdisk -l /dev/sda
```

Create a GUID partition table, a 4GB EFI system partition, and a Linux LUKS partition in the remainder of the device (replace `/dev/sda` accordingly):

```bash
gdisk /dev/sda
o
n
+4G
ef00
n
8309
w
```

---

Next: [Erase the partitions](8-erase.md)
