# Wireshark Examples

## Example 1: Analyze DNS Traffic

Start a capture.

Visit a website.

Apply filter:

```text
dns
```

Observe:

- DNS Query
- DNS Response
- Requested Domain
- Returned IP Address

---

## Example 2: HTTP Request

Visit a local HTTP website.

Filter:

```text
http
```

Inspect:

- GET request
- Response headers
- Status code
- Host header

---

## Example 3: ICMP Ping

Open a terminal:

```bash
ping google.com
```

Apply filter:

```text
icmp
```

Observe:

- Echo Request
- Echo Reply
- Sequence Numbers

---

## Example 4: TCP Three-Way Handshake

Filter:

```text
tcp.flags.syn == 1
```

Observe:

```
SYN
SYN-ACK
ACK
```

This establishes a TCP connection.

---

## Example 5: Follow TCP Stream

Right-click any TCP packet.

Choose:

```
Follow
→ TCP Stream
```

Purpose:

- Reconstruct conversations
- Understand application communication

---

## Example 6: Packet Details

Expand:

- Ethernet II
- Internet Protocol
- TCP
- Application Protocol

Observe how each protocol adds its own header.

---

## Example 7: Statistics

Navigate to:

```
Statistics
→ Protocol Hierarchy
```

Useful for:

- Traffic composition
- Protocol usage
- Packet counts
