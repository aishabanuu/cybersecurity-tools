# John the Ripper

> John the Ripper (JtR) is one of the most popular offline password crackers.
> It automatically detects hash types and supports wordlist, brute-force, and rule-based attacks.

---

## Quick Summary

| Item | Detail |
|------|--------|
| Type | Offline password / hash cracker |
| Pre-installed on Kali | ✅ Yes |
| Best for | CTFs, cracking shadow files, hash challenges |
| Wordlist used | rockyou.txt |
| Docs | https://www.openwall.com/john/ |

---

## Files in This Folder

| File | Contents |
|------|----------|
| `installation.md` | How to install and verify John |
| `commands.md` | All important commands and flags |
| `examples.md` | Step-by-step experiments |
| `notes.md` | Key concepts, tips, and lessons learned |

---

## Quickstart

```bash
# Create a test MD5 hash
echo -n "password123" | md5sum | awk '{print $1}' > hash.txt

# Crack it
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt

# Show result
john --show --format=raw-md5 hash.txt
```
