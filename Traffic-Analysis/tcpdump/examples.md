# tcpdump Examples

## Example 1: Capture 10 Packets

```bash
sudo tcpdump -c 10
```

Purpose:

- Learn packet structure
- Observe network activity

---

## Example 2: Capture DNS Requests

```bash
sudo tcpdump port 53
```

Generate traffic:

```bash
nslookup google.com
```

Observe:

- DNS queries
- DNS responses

---

## Example 3: Capture ICMP Traffic

Start capture:

```bash
sudo tcpdump icmp
```

Generate traffic:

```bash
ping google.com
```

Observe:

- Echo Request
- Echo Reply

---

## Example 4: Save a PCAP

Capture traffic:

```bash
sudo tcpdump -i wlan0 -w dns-capture.pcap
```

Open later in Wireshark:

```text
File
→ Open
→ dns-capture.pcap
```

Purpose:

- Capture on servers
- Analyze on another system

---

## Example 5: Read a Saved Capture

```bash
tcpdump -r dns-capture.pcap
```

Useful for:

- Reviewing captures
- Sharing captures
- Incident investigation

---

## Example 6: Capture HTTP Traffic

```bash
sudo tcpdump port 80
```

Visit an HTTP website and observe:

- Client request
- Server response
- Packet sequence

---

## Example 7: Inspect Packet Contents

```bash
sudo tcpdump -A port 80
```

Purpose:

- View application-layer data
- Understand HTTP requests
