# tcpdump Notes

## What is tcpdump?

tcpdump is a packet capture utility that uses **libpcap** to capture and display network packets directly from a network interface.

It is commonly used for:

- Network troubleshooting
- Incident response
- Security investigations
- Traffic monitoring

---

## Key Concepts

### Network Interface

The device through which packets are captured.

Examples:

```text
eth0
wlan0
lo
```

---

### Capture Filter

A capture filter limits which packets are collected.

Examples:

```text
host 192.168.1.10
port 80
icmp
tcp
udp
```

Using filters reduces unnecessary traffic and makes analysis easier.

---

### PCAP Files

Captured packets can be saved in the PCAP format.

Example:

```bash
sudo tcpdump -w capture.pcap
```

These files can later be opened in Wireshark for graphical analysis.

---

### Verbose Output

Verbosity levels provide additional packet information.

| Option | Description |
|---------|-------------|
| `-v` | Verbose |
| `-vv` | More verbose |
| `-vvv` | Maximum verbosity |

---

## Common Filters

| Filter | Purpose |
|---------|---------|
| `host 192.168.1.10` | Specific host |
| `src 192.168.1.10` | Source host |
| `dst 192.168.1.10` | Destination host |
| `port 80` | HTTP traffic |
| `port 53` | DNS traffic |
| `icmp` | Ping packets |
| `tcp` | TCP packets |
| `udp` | UDP packets |

---

## Best Practices

- Capture only the traffic you need.
- Use capture filters to reduce noise.
- Save important captures.
- Analyze saved PCAPs with Wireshark.
- Label captures clearly with dates and descriptions.

---

## Personal Notes

- Learn tcpdump alongside Wireshark—they complement each other.
- Practice identifying interfaces before capturing traffic.
- Keep capture sessions short to avoid excessively large PCAP files.
- Use verbose output to better understand packet details.
- Archive interesting captures for future study and comparison.
