# SQLMap Installation

## Verify Installation

Check whether SQLMap is installed:

```bash
sqlmap --version
```

---

## Install SQLMap

On Kali Linux:

```bash
sudo apt update
sudo apt install sqlmap
```

---

## Verify Installation

```bash
sqlmap --version
```

Example Output:

```text
sqlmap 1.x.x
```

---

## Display Help

```bash
sqlmap -h
```

---

## Update SQLMap

```bash
sudo apt update
sudo apt upgrade sqlmap
```

---

## Verify Network Connectivity

Example:

```bash
curl http://localhost
```

or

```bash
curl http://127.0.0.1
```

Ensure the lab application is reachable before beginning testing.

## Recommended Lab Targets

- DVWA
- OWASP Juice Shop
- WebGoat
- Personal development environments

Only test systems within your authorized scope.
