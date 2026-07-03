# Wireshark Notes

## Packet Structure

Each packet is divided into layers.

```
Frame
   ↓
Ethernet
   ↓
IP
   ↓
TCP/UDP
   ↓
Application Data
```

---

## Packet Pane Layout

Wireshark displays three panes.

### Packet List

Summary of every packet.

Shows:

- Number
- Time
- Source
- Destination
- Protocol
- Length
- Info

---

### Packet Details

Displays protocol headers.

Example:

```
Ethernet II
Internet Protocol
Transmission Control Protocol
Hypertext Transfer Protocol
```

---

### Packet Bytes

Displays raw hexadecimal data.

Useful for:

- Low-level analysis
- Understanding packet encoding

---

## Color Coding

Wireshark highlights packets using colors.

Examples:

- TCP
- HTTP
- DNS
- ICMP
- Errors

Colors help quickly identify different traffic types.

---

## Common Protocols

| Protocol | Purpose |
|----------|----------|
| ARP | Address Resolution |
| ICMP | Network Diagnostics |
| TCP | Reliable Communication |
| UDP | Fast Communication |
| DNS | Name Resolution |
| HTTP | Web Traffic |
| HTTPS | Secure Web Traffic |
| TLS | Encryption |

---

## Useful Menu Options

### Statistics

Shows:

- Endpoints
- Conversations
- Protocol Hierarchy
- IO Graphs

---

### Analyze

Useful for:

- Following Streams
- Expert Information
- Packet Comments

---

### File

Used to:

- Save PCAPs
- Export Packets
- Import Captures

---

## Best Practices

- Capture only relevant traffic.
- Apply display filters early.
- Label packet captures.
- Save important PCAP files.
- Compare multiple protocols.

---

## Personal Notes

- Learn TCP thoroughly before studying higher-level protocols.
- Spend time understanding packet headers.
- Memorize common display filters.
- Follow TCP streams regularly.
- Practice analyzing your own network traffic.
- Save screenshots of interesting packet captures for documentation.
