# 27 - Network configuration

Previous: [Reboot the system](26-reboot.md)

References:

- <https://wiki.archlinux.org/title/Network_configuration>

---

Login as a regular user and use `sudo` to execute commands as superuser.

We will configure the network to connect automatically to the internet.

We describe two options for network manager:

- NetworkManager - recommended if you connect to different networks (in a laptop)
- Systemd-networkd - recommended for a static connection (in a desktop)

## NetworkManager

Use `networkmanager` as the network manager (we have already installed it):

- <https://wiki.archlinux.org/title/NetworkManager>

Enable

```bash
sudo systemctl enable NetworkManager.service --now
```

After reboot, check status:

```bash
systemctl status NetworkManager.service
```

(Wired) Ethernet connections with DHCP are automatically configured and should work out of the box (NetworkManager will auto-connect in the future).

## Systemd-networkd

Use `systemd-networked` as the network manager:

- <https://wiki.archlinux.org/title/Systemd-networkd>
- <https://wiki.archlinux.org/title/Systemd-networkd#Wireless_adapter>

Networkd is already installed on the computer as it is part of systemd.

(Wired) Create a config file for a wired adapter:

```bash
sudo nano /etc/systemd/network/20-wired.network
```

Add (replace `enp3s0f0` accordingly)

```
[Match]
Name=enp3s0f0

[Link]
RequiredForOnline=routable
Multicast=true

[Network]
DHCP=yes
MulticastDNS=yes
```

(Wireless) Create a config file for a wireless adapter:

```bash
sudo nano /etc/systemd/network/25-wireless.network
```

Add (replace `wlan0` accordingly)

```
[Match]
Name=wlan0

[Link]
RequiredForOnline=routable
Multicast=true

[Network]
DHCP=yes
MulticastDNS=yes
IgnoreCarrierLoss=3s
```

Enable

```bash
sudo systemctl enable systemd-networkd.service --now
```

After reboot, check status with

```bash
networkctl
```

and

```bash
networkctl status
```

## Wireless authentication

(With Systemd-networkd only) Use `iwd` to authenticate (we have already installed it):

- <https://wiki.archlinux.org/title/Iwd>

Enable

```bash
sudo systemctl enable iwd.service --now
```

After reboot, check status:

```bash
systemctl status iwd.service
```

## DNS configuration

(With NetworkManager or Systemd-networkd) Use `systemd-resolved` to manage DNS:

 - <https://wiki.archlinux.org/title/Systemd-resolved#DNS>

Resolved is already installed on the computer as it is part of systemd.

Enable

```bash
sudo systemctl enable systemd-resolved.service --now
```

Replace `/etc/resolve.conf` with a symbolic link to `stub-resolv.conf`:

```bash
sudo ln -sf /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf
```

After reboot, check status:

```bash
resolvectl status
```

## mDNS configuration

Use `systemd-resolved` to manage mDNS:

- <https://wiki.archlinux.org/title/Systemd-resolved#mDNS>

It is enabled by default with systemd-resolved. For systemd-networked, the interfaces must be configured to use mDNS as described above (with MulticastDNS=yes and Multicast=true).

After reboot, try local DNS resolution with (replace `myhostname` accordingly)

```bash
ping -c 3 myhostname.local
```

## Timesyncd

Use `systemd-timesync` to manage time synchromization:

- <https://wiki.archlinux.org/title/Systemd-timesyncd>

Timesyncd is already installed on the computer as it is part of systemd.

Edit the config file:

```bash
sudo nano /etc/systemd/timesyncd.conf
```

Add

```
NTP=time.google.com
```

Enable

```bash
sudo systemctl enable systemd-timesyncd.service --now
```

After reboot, check status with

```bash
timedatectl status
```

or

```bash
timedatectl timesync-status --all
```

## Connect to wifi

### Iwd

(With Systemd-networkd and iwd only) Use the client `iwctl`:

- <https://wiki.archlinux.org/title/Iwd#iwctl>

First, check for software blocks (to avoid errors):

```bash
rfkill list
```

Look for "Soft blocked: yes" or "Hard blocked: yes" next to your wireless device. Unblock the device (actually, all the devices):

```bash
rfkill unblock all
```

Run `rfkill list` again to confirm that the block is gone.

In the command line, enter the following (replace `wlan0` and `SSID` accordingly):

```bash
iwctl
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect SSID
station wlan0 show
quit
```

Note: To connect to a network with spaces in the SSID, the network name should be double quoted (for example, "my network").

The program iwd automatically stores network passphrases in the `/var/lib/iwd` directory and uses them to auto-connect in the future.

Internet connection should work. Check the connection with

```bash
ping -c 3 www.google.com
```

### NetworkManager

(With NetworkManager only) Use the client `nmcli`:

- <https://wiki.archlinux.org/title/NetworkManager#Usage>

In the command line, enter the following commands (replace `SSID` and `mypassword` accordingly):

```bash
nmcli device wifi list
nmcli device wifi connect SSID password mypassword
nmcli connection show
```

The program NetworkManager automatically stores network passphrases in the `/etc/NetworkManager/system-connections/` directory and uses them to auto-connect in the future.

Internet connection should work. Check the connection:

```bash
ping -c 3 www.google.com
```

## Check status

To verify that automatic connection is working, reboot the system:

```bash
sudo reboot
```

Login as user an execute the following commands (verify the output):

```bash
ping -c 3 www.google.com
```

(With Systemd-networkd and iwd only) :

```bash
ping -c 3 www.google.com
resolvectl status
networkctl
networkctl status
systemctl status iwd.service
timedatectl status
timedatectl timesync-status --all
```

(With NetworkManager):

```bash
ping -c 3 www.google.com
resolvectl status
systemctl status NetworkManager.service
timedatectl status
timedatectl timesync-status --all
```

To check swap, execute

```bash
systemctl status systemd-zram-setup@zram0.service
zramctl
swapon --show
```

---

Next: [Install a graphical environment](28-graphical.md)
