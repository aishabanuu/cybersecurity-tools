# Wireshark Installation

## Verify Installation

Check whether Wireshark is installed:

```bash
wireshark --version
```

---

## Install on Kali Linux

```bash
sudo apt update
sudo apt install wireshark
```

---

## Launch Wireshark

Terminal:

```bash
wireshark
```

or

Applications → Wireshark

---

## Allow Packet Capture

If prompted:

```
Should non-superusers be able to capture packets?

Yes
```

Add your user to the Wireshark group:

```bash
sudo usermod -aG wireshark $USER
```

Apply changes:

```bash
newgrp wireshark
```

---

## Verify Interfaces

Open Wireshark.

You should see interfaces such as:

- eth0
- wlan0
- lo (Loopback)

---

## Selecting an Interface

Choose the interface carrying traffic.

Examples:

- Wi-Fi → wlan0
- Ethernet → eth0
- Local testing → lo

---

## Verify Capture

Double-click an interface.

Packets should begin appearing immediately.
