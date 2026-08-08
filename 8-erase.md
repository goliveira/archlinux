# 8 - Erase the partition (optional)

Previous: [Partition the disks](7-partition.md)

References:

- <https://wiki.archlinux.org/title/Dm-crypt/Drive_preparation#dm-crypt_wipe_on_an_empty_device_or_partition>

---

If you don't need to erase the partition, go to [9-format](9-format.md).

First, create a temporary encrypted container on the partition or complete device to be erased (replace `/dev/sda2` accordingly):

```bash
cryptsetup open --type=plain --key-file=/dev/urandom --sector-size=4096 /dev/sda2 to_be_wiped
```

You can verify that the container was created with

```bash
lsblk -f
```

Wipe the container with zeros by executing

```bash
dd bs=1M if=/dev/zero of=/dev/mapper/to_be_wiped status=progress
```

The above comand will run until the device is full:

```
dd: writing to ‘/dev/mapper/to_be_wiped’: No space left on device
```

Finally, close the temporary container:

```bash
cryptsetup close to_be_wiped
```

---

Next: [Format the partitions](9-format.md)
