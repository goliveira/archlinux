# 2 - Verify the ISO file (optional)

Previous: [Acquire an installation image](1-acquire.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Verify_signature>

---

This step is optional (but recommended). We will verify that the ISO file is not damaged and has not been modified. To do this, we will use `gpg` and `b2sum`. Both programs are typically pre-installed on Linux, as they are part of the core utilities. The following commands check the b2sum and verify the signature of the ISO file:

```bash
b2sum -c b2sums.txt
gpg --keyserver-options auto-key-retrieve --verify archlinux-x86_64.iso.sig
```

We will get an error message corresponding to the files that we did not download. Ignore these messages. The relevant output lines are the following:

```
archlinux-x86_64.iso: OK
gpg: Good signature from "Pierre Schmitz <pierre@archlinux.org>" [unknown]
```

After verifying the file, you may delete the keys that you retrieved by executing (two times)

```bash
gpg --delete-keys Pierre
gpg --delete-keys Pierre
```

Check that the keys are removed with

```bash
gpg -k
```

Alternatively, from an existing Arch Linux installation run

```bash
b2sum -c b2sums.txt
pacman-key -v archlinux-x86_64.iso.sig
```

---

Next: [Prepare an installation media](3-prepare.md)
