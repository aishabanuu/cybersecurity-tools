# tcpdump Installation

## Verify Installation

Check if tcpdump is installed:

```bash
tcpdump --version
```

---

## Install on Kali Linux

```bash
sudo apt update
sudo apt install tcpdump
```

---

## Verify Installation

```bash
which tcpdump
```

Example Output:

```text
/usr/bin/tcpdump
```

---

## View Help

```bash
tcpdump --help
```

---

## List Available Interfaces

```bash
ip a
```

or

```bash
tcpdump -D
```

Example Output:

```text
1.eth0
2.wlan0
3.lo
```

---

## Check Permissions

Packet capture usually requires elevated privileges.

Example:

```bash
sudo tcpdump
```

---

## Verify Capture

Capture a few packets:

```bash
sudo tcpdump -i wlan0
```

Replace `wlan0` with your network interface if necessary.
