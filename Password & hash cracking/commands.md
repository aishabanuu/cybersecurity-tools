# ⌨️ John the Ripper — Commands

## Basic Syntax
```bash
john [options] <hashfile>
```

---

## Most Used Commands

### Wordlist attack (most common)
```bash
john --format=<hash_type> --wordlist=<wordlist> <hashfile>
```

### Brute force attack
```bash
john --format=<hash_type> --incremental <hashfile>
```

### Show cracked passwords
```bash
john --show --format=<hash_type> <hashfile>
```

### Auto-detect hash type
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt <hashfile>
```

### List all supported formats
```bash
john --list=formats
```

### Use rules (mutates wordlist entries)
```bash
john --format=<hash_type> --wordlist=<wordlist> --rules <hashfile>
```

### Crack Linux shadow file
```bash
unshadow /etc/passwd /etc/shadow > combined.txt
john --wordlist=/usr/share/wordlists/rockyou.txt combined.txt
```

### Resume an interrupted session
```bash
john --restore
```

---

## Common Hash Format Flags

| Flag | Hash Type |
|------|-----------|
| `--format=raw-md5` | MD5 |
| `--format=raw-sha1` | SHA1 |
| `--format=raw-sha256` | SHA256 |
| `--format=sha512crypt` | Linux SHA512 (`$6$`) |
| `--format=nt` | Windows NTLM |
| `--format=bcrypt` | bcrypt (`$2b$`) |
| `--format=zip` | ZIP file password |

---

## Useful Flags

| Flag | What it does |
|------|-------------|
| `--wordlist=` | Path to wordlist file |
| `--format=` | Specify hash type manually |
| `--rules` | Apply mangling rules to wordlist |
| `--incremental` | Full brute force mode |
| `--show` | Display cracked passwords |
| `--restore` | Resume a stopped session |
| `--session=name` | Name a session to restore later |
| `--fork=4` | Use 4 CPU cores |

---

## John's Saved Results

John stores cracked hashes in:
```bash
~/.john/john.pot
cat ~/.john/john.pot    # view all previously cracked hashes
```
