# Wireshark Display Filters

Display filters help isolate packets of interest.

---

## Filter by IP Address

```text
ip.addr == 192.168.1.10
```

---

## Source IP

```text
ip.src == 192.168.1.10
```

---

## Destination IP

```text
ip.dst == 192.168.1.10
```

---

## TCP Only

```text
tcp
```

---

## UDP Only

```text
udp
```

---

## DNS Traffic

```text
dns
```

---

## HTTP Traffic

```text
http
```

---

## HTTPS (TLS)

```text
tls
```

---

## ICMP (Ping)

```text
icmp
```

---

## ARP

```text
arp
```

---

## TCP Port

```text
tcp.port == 80
```

---

## UDP Port

```text
udp.port == 53
```

---

## HTTP GET Requests

```text
http.request.method == "GET"
```

---

## HTTP Responses

```text
http.response
```

---

## DNS Queries

```text
dns.flags.response == 0
```

---

## DNS Responses

```text
dns.flags.response == 1
```

---

## TCP SYN Packets

```text
tcp.flags.syn == 1
```

---

## TCP Retransmissions

```text
tcp.analysis.retransmission
```

---

## Packet Length

```text
frame.len > 1000
```

---

## Combine Filters

```text
ip.addr == 192.168.1.10 && tcp
```

---

## Filter Tips

- Keep filters simple.
- Filter one protocol at a time.
- Verify timestamps.
- Use Follow TCP Stream for HTTP traffic.
