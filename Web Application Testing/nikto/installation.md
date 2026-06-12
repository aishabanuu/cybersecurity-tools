# Nikto Installation

## Verify Installation

Check whether Nikto is installed:

```bash
nikto -Version
```

---

## Install Nikto

On Kali Linux:

```bash
sudo apt update
sudo apt install nikto
```

---

## Verify Installation

```bash
nikto -Version
```

Expected output:

```text
Nikto vX.X.X
```

---

## Display Help

```bash
nikto -Help
```

---

## Update Package Sources

```bash
sudo apt update
```

---

## Verify Connectivity

Before scanning a lab target:

```bash
curl http://localhost
```

or

```bash
curl https://localhost
```

This confirms the web service is reachable.

## Recommended Practice Targets

- Local web servers
- DVWA
- OWASP Juice Shop
- Personal lab environments

Only test systems you own or have permission to assess.
