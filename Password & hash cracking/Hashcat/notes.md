# 📝 Hashcat — Notes & Lessons Learned

## Hashcat vs John the Ripper

| | Hashcat | John the Ripper |
|-|---------|-----------------|
| Speed | Faster (GPU) | Slower (CPU) |
| Ease of use | Slightly more flags | More beginner-friendly |
| Auto hash detect | ❌ Must specify `-m` | ✅ Auto-detects |
| Best for | Large jobs, speed | Quick CTF hashes |
| Supported formats | 300+ | 400+ |

**Rule of thumb:** Use John for quick CTF hashes; use Hashcat when you need speed or advanced attack modes.

---

## The Potfile

Hashcat stores cracked passwords in:
```
~/.local/share/hashcat/hashcat.potfile
```
Once a hash is cracked, it's in the potfile — Hashcat won't re-crack it.
If you want to re-run an experiment:
```bash
# Remove just one hash from potfile manually, or clear all:
rm ~/.local/share/hashcat/hashcat.potfile
```

---

## Understanding Masks

Masks let you define the exact shape of a password:

| Password shape | Mask |
|----------------|------|
| 4 lowercase letters | `?l?l?l?l` |
| 4-digit PIN | `?d?d?d?d` |
| 6 any characters | `?a?a?a?a?a?a` |
| Word + 2 digits | Use wordlist + `-a 6 wordlist.txt ?d?d` |

The longer the mask, the exponentially longer it takes.

---

## Tips From Practice

- Always add `--force` inside a VM
- Use `-m 0` for MD5, but check the hash type with `hashid` if unsure
- `--show` won't show results until the attack finishes or is stopped
- The `best64.rule` file covers the most common real-world password mutations
- Save results to a file with `-o cracked.txt` on long jobs
- Use `--status` during a run to see live progress (or press `s` key)

---

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| "No hashes loaded" | Hash was already cracked — delete potfile and retry |
| Errors about OpenCL | Add `--force` to use CPU mode in VM |
| `--show` returns empty | Attack may still be running, or wrong `-m` type |
| Very slow brute force | Narrow your mask — don't use `?a` for long passwords |

---

## Defensive Takeaways

- bcrypt (`-m 3200`) is deliberately slow — hashcat can only try ~100/sec vs billions for MD5
- Salting defeats precomputed rainbow tables but not targeted wordlist attacks
- The best defense is a **long, random, unique password** + **proper algorithm (bcrypt/Argon2)**
- Password managers generate and store uncrackable random passwords automatically

---

## References

- Official wiki: https://hashcat.net/wiki/
- Hash mode list: https://hashcat.net/wiki/doku.php?id=hashcat
- Rules collection: `/usr/share/hashcat/rules/`
- Example hashes: `hashcat --example-hashes`
