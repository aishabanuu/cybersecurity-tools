# Nmap Notes

## Key Concepts

### Host Discovery

Determines whether a host is alive before scanning ports.

Common option:

```bash
-sn
```

### Port Scanning

Identifies open TCP or UDP ports.

### Service Enumeration

Determines:

- Service name
- Version
- Product information

Option:

```bash
-sV
```

### OS Detection

Attempts to identify operating system characteristics.

Option:

```bash
-O
```

### NSE (Nmap Scripting Engine)

Allows automated enumeration and security checks.

Examples:

```bash
--script default
```

```bash
--script vuln
```

## Important Ports

| Port | Service |
|--------|---------|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 110 | POP3 |
| 139 | NetBIOS |
| 143 | IMAP |
| 443 | HTTPS |
| 445 | SMB |
| 3306 | MySQL |
| 3389 | RDP |

## Personal Notes

- Start with host discovery.
- Save scan results.
- Document findings immediately.
- Verify unusual services.
- Use NSE scripts for deeper enumeration.
