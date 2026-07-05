# tcpdump Commands

## Display Help

```bash
tcpdump --help
```

---

## List Interfaces

```bash
tcpdump -D
```

---

## Capture on Default Interface

```bash
sudo tcpdump
```

---

## Capture on Specific Interface

```bash
sudo tcpdump -i wlan0
```

---

## Capture a Limited Number of Packets

```bash
sudo tcpdump -c 20
```

---

## Save Packets to a PCAP File

```bash
sudo tcpdump -i wlan0 -w capture.pcap
```

---

## Read a PCAP File

```bash
tcpdump -r capture.pcap
```

---

## Capture DNS Traffic

```bash
sudo tcpdump port 53
```

---

## Capture HTTP Traffic

```bash
sudo tcpdump port 80
```

---

## Capture HTTPS Traffic

```bash
sudo tcpdump port 443
```

---

## Capture ICMP (Ping)

```bash
sudo tcpdump icmp
```

---

## Capture Traffic From a Host

```bash
sudo tcpdump host 192.168.1.10
```

---

## Capture Source Host

```bash
sudo tcpdump src 192.168.1.10
```

---

## Capture Destination Host

```bash
sudo tcpdump dst 192.168.1.10
```

---

## Increase Verbosity

```bash
sudo tcpdump -v
```

More verbose:

```bash
sudo tcpdump -vv
```

Most verbose:

```bash
sudo tcpdump -vvv
```

---

## Display Packets in ASCII

```bash
sudo tcpdump -A
```

---

## Display Packets in Hexadecimal

```bash
sudo tcpdump -X
```
