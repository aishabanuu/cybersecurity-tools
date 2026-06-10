# Netdiscover Examples

## Example 1: Discover Devices on Local Network

```bash
sudo netdiscover
```

Sample Output:

```text
Currently scanning: 192.168.1.0/24

IP Address      MAC Address         Vendor
-------------------------------------------------------
192.168.1.1     AA:BB:CC:11:22:33   Router Vendor
192.168.1.10    DD:EE:FF:44:55:66   Dell Inc.
192.168.1.15    11:22:33:44:55:66   Apple Inc.
```

---

## Example 2: Scan a Specific Subnet

```bash
sudo netdiscover -r 192.168.1.0/24
```

Purpose:

- Identify active hosts
- Discover unknown devices
- Build a network inventory

---

## Example 3: Passive Monitoring

```bash
sudo netdiscover -p
```

Purpose:

- Observe ARP traffic
- Identify active devices
- Avoid generating active scan traffic

---

## Example 4: Use with Nmap

Discover hosts:

```bash
sudo netdiscover -r 192.168.1.0/24
```

Then enumerate services:

```bash
sudo nmap -sV 192.168.1.10
```

This is a common workflow during network reconnaissance.

---

## Example 5: Identify Device Vendor

Output:

```text
192.168.1.25  00:1A:2B:3C:4D:5E
```

Netdiscover may resolve the MAC address to:

```text
Cisco Systems
```

This can help identify device types before deeper enumeration.
