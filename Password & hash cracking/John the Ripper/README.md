# ⚡ Hashcat

> Hashcat is the world's fastest password cracker, using your GPU for massive parallelism.
> It supports 300+ hash types and multiple attack modes.

---

## 📋 Quick Summary

| Item | Detail |
|------|--------|
| Type | Offline GPU-accelerated hash cracker |
| Pre-installed on Kali | ✅ Yes |
| Best for | Large hash lists, fast cracking, advanced attacks |
| Wordlist used | rockyou.txt |
| Docs | https://hashcat.net/wiki/ |

---

## 📁 Files in This Folder

| File | Contents |
|------|----------|
| `installation.md` | How to install and verify Hashcat |
| `commands.md` | All important commands, modes, and flags |
| `examples.md` | Step-by-step experiments |
| `notes.md` | Key concepts, tips, and lessons learned |

---

## ⚡ Quickstart

```bash
# Create test hashes
echo -n "sunshine" | md5sum | awk '{print $1}' > hashes.txt

# Crack with wordlist
hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt --force

# Show results
hashcat -m 0 hashes.txt --show
```

> Use `--force` when running inside a VM (GPU not available, forces CPU mode)
