# ⌨️ Hashcat — Commands

## Basic Syntax
```bash
hashcat -m <hash_type> -a <attack_mode> <hashfile> [wordlist/mask]
```

---

## Attack Modes (-a)

| Mode | Flag | Description |
|------|------|-------------|
| Wordlist | `-a 0` | Try every word in a list |
| Combination | `-a 1` | Combine two wordlists |
| Brute force | `-a 3` | Try all combinations with a mask |
| Rule-based | `-a 0 -r` | Wordlist + mutation rules |

---

## Common Hash Types (-m)

| Code | Hash Type |
|------|-----------|
| `0` | MD5 |
| `100` | SHA1 |
| `1400` | SHA256 |
| `1700` | SHA512 |
| `1800` | SHA512crypt — Linux `$6$` |
| `1000` | NTLM — Windows |
| `3200` | bcrypt |
| `500` | MD5crypt — Linux `$1$` |

---

## Most Used Commands

### Wordlist attack
```bash
hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt --force
```

### Brute force with mask
```bash
# ?l = lowercase, ?u = uppercase, ?d = digit, ?s = symbol, ?a = all
hashcat -m 0 -a 3 hashes.txt ?a?a?a?a?a?a --force   # 6-char all types
hashcat -m 0 -a 3 hashes.txt ?d?d?d?d --force        # 4-digit PIN
```

### Rule-based attack
```bash
hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule --force
```

### Show cracked results
```bash
hashcat -m 0 hashes.txt --show
```

### List all supported hash modes
```bash
hashcat --help | grep -i md5
hashcat --example-hashes | less
```

---

## Mask Character Sets

| Mask | Matches |
|------|---------|
| `?l` | Lowercase letters (a-z) |
| `?u` | Uppercase letters (A-Z) |
| `?d` | Digits (0-9) |
| `?s` | Symbols (!@#$ etc.) |
| `?a` | All of the above |

**Example — crack a password like `Pass1!`:**
```bash
hashcat -m 0 -a 3 hashes.txt ?u?l?l?l?d?s --force
```

---

## Useful Flags

| Flag | What it does |
|------|-------------|
| `--force` | Run in CPU mode (needed in VMs) |
| `--show` | Display already-cracked hashes |
| `--status` | Show live progress |
| `-o output.txt` | Save results to file |
| `--remove` | Remove cracked hashes from list |
| `-r rules.rule` | Apply rules file |
| `--runtime=60` | Stop after 60 seconds |
