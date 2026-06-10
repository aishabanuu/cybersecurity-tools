# Nmap Examples

## Example 1: Discover Hosts

```bash
nmap -sn 192.168.1.0/24
```

Sample Result:

```text
Host: 192.168.1.1
Host: 192.168.1.10
Host: 192.168.1.15
```

---

## Example 2: Service Enumeration

```bash
sudo nmap -sV 192.168.1.10
```

Sample Output:

```text
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH
80/tcp   open  http    Apache
443/tcp  open  https   Apache
```

---

## Example 3: Operating System Detection

```bash
sudo nmap -O 192.168.1.10
```

Sample Output:

```text
Running: Linux
OS details: Linux Kernel 5.x
```

---

## Example 4: Full Assessment Scan

```bash
sudo nmap -A 192.168.1.10
```

Provides:

- Service versions
- OS detection
- Script scanning
- Traceroute

---

## Example 5: Save Scan Results

```bash
nmap -sV 192.168.1.10 -oN service-scan.txt
```

Output file:

```text
service-scan.txt
```
