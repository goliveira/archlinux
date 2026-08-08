# 11 - Connect to the network

Previous: [Mount the partitions](10-mount.md)

References:

- <https://wiki.archlinux.org/title/Installation_guide#Connect_to_the_internet>

---

Connect to the network:

(Ethernet) If you booted the live environment with the Ethernet cable connected, dynamic IP address and DNS server assignment should work out of the box. Test your connection with

```bash
ping -c 3 www.google.com
```

If you plugged the cable latter, find your Ethernet card name with

```bash
ip link
```

Then execute (replace `eth0` accordingly):

```bash
dhcpcd eth0
```

(Wireless) Authenticate to the wireless network following the instructions below. We will describe how to connect to the network using `ip`, `iwctl` and `dhcpcd`.

To avoid errors, first check for software blocks:

```bash
rfkill list
```

Look for "Soft blocked: yes" or "Hard blocked: yes" next to your wireless device. Unblock the device (actually, all the devices):

```bash
rfkill unblock all
```

Run `rfkill list` again to confirm that the block is gone.

Check the network connection with `ip`:

```bash
ip addr
```

(Wireless) Turn on network device (replace `wlan0` accordingly):

```bash
ip link
ip link set wlan0 up
ip link show wlan0
```

(Wireless) In the live environment, the `iwd` service is enabled by default. Check the status with

```bash
systemclt status iwd.service
```

(Wireless) Connect to wi-fi using `iwctl` (replace `wlan0` and `network_name` accordingly):

```bash
iwctl
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect network_name
station wlan0 show
quit
```

Note: To connect to a network with spaces in the SSID, the network name should be double quoted (for example, "my network").

Get a dynamic  IP address with `dhcpcd` (replace `wlan0` accordingly):

```bash
dhcpcd wlan0
```

Alternatively, get a static IP address (replace `eth0` accordingly):

```bash
dhcpcd -S ip_address=123.123.25.123/24 -S routers=123.123.25.123 -S domain_name_servers=8.8.8.8 eth0
```

Test the internet connection:

```bash
ping -c 3 www.google.com
```

---

Next: [Update the system clock](12-clock.md)
