# General Notes

## What is Traffic Analysis?

Traffic analysis is the process of capturing, inspecting, and interpreting network packets to understand how systems communicate.

It helps security professionals:

- Troubleshoot networks
- Detect malicious activity
- Investigate incidents
- Understand protocols
- Analyze application behavior

---

# What is a Packet?

A packet is a unit of data transmitted across a network.

Typical packet components include:

- Ethernet Header
- IP Header
- Transport Header (TCP/UDP)
- Payload

---

# Packet Flow

```text
Application
     ↓
Transport Layer
     ↓
Network Layer
     ↓
Data Link Layer
     ↓
Physical Network
```

---

# Common Protocols

| Protocol | Purpose | Default Port |
|-----------|----------|--------------|
| ARP | Address Resolution | — |
| ICMP | Diagnostics | — |
| TCP | Reliable Transport | Various |
| UDP | Fast Transport | Various |
| DNS | Name Resolution | 53 |
| HTTP | Web Traffic | 80 |
| HTTPS | Secure Web Traffic | 443 |
| TLS | Encryption | 443 |

---

# Typical Analysis Workflow

```text
Capture Traffic
        ↓
Apply Filters
        ↓
Inspect Packets
        ↓
Follow Conversations
        ↓
Identify Anomalies
        ↓
Document Findings
```

---

# Common Packet Information

Every packet contains useful information such as:

- Source IP
- Destination IP
- Source Port
- Destination Port
- Protocol
- Packet Length
- Timestamp

---

# Why Learn Packet Analysis?

Packet analysis helps you:

- Understand network communication
- Detect suspicious traffic
- Troubleshoot connectivity issues
- Analyze malware behavior
- Investigate security incidents

---

# Best Practices

- Capture only what you need.
- Label and organize PCAP files.
- Document observations.
- Verify findings with multiple tools.
- Practice with different protocols.

---

# Personal Notes

- Learn protocols before memorizing filters.
- Practice reading packets manually.
- Compare GUI (Wireshark) and CLI (tcpdump) analysis.
- Save interesting packet captures for future reference.
- Build confidence by analyzing normal network traffic before studying suspicious activity.
