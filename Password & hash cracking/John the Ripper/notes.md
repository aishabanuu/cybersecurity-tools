# 📝 John the Ripper — Notes & Lessons Learned

## Key Concepts

### Why MD5/SHA1 are bad for passwords
MD5 and SHA1 are designed to be **fast** — a CPU can compute billions per second.
That speed is great for checksums but terrible for password storage.
John can crack common MD5 passwords in under a second.

### What makes a password hard to crack
- Not in any wordlist (random characters)
- Long (each extra character multiplies the brute-force time exponentially)
- Mixed character sets (upper + lower + digits + symbols)
- Proper hashing algorithm: bcrypt, Argon2, scrypt (these are **slow by design**)

### What is salting?
A **salt** is a random string added to the password before hashing:
```
hash(password + salt) → stored_hash
```
This means even if two users have the same password, their hashes are different.
It also defeats rainbow table attacks completely.

---

## John's Attack Modes

| Mode | Command | When to use |
|------|---------|-------------|
| Wordlist | `--wordlist=` | First attempt, fastest |
| Rules | `--wordlist= --rules` | When wordlist alone fails |
| Incremental | `--incremental` | Last resort, very slow |
| Single | `--single` | Uses username/GECOS as hints |

---

## Tips From Practice

- Always try `--wordlist` first before brute force — it's 100x faster
- If `--wordlist` fails, try `--rules` next — many users just add `1` or `!` to a word
- Check `~/.john/john.pot` — previously cracked hashes are cached there
- Use `--fork=4` to use multiple CPU cores and speed things up
- If you don't know the hash type, let John auto-detect: don't use `--format`
- Use `hashid <hash>` or `hash-identifier` when unsure of the format

---

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Hash already cracked, John says "No password hashes loaded" | Clear pot: `rm ~/.john/john.pot` |
| Wrong `--format` flag | Let John auto-detect, or use `hashid` |
| rockyou.txt still zipped | `sudo gunzip /usr/share/wordlists/rockyou.txt.gz` |
| Output shows nothing after `--show` | Check you're using the right `--format` with `--show` |

---

## Defensive Takeaways

- Use **bcrypt** or **Argon2** for storing passwords — they're slow by design
- Always **salt** hashes — even if two users share a password, hashes differ
- A password not in any wordlist + random characters = practically uncrackable with John
- Monitor `/etc/shadow` permissions — it should be readable only by root

---

## References

- Official docs: https://www.openwall.com/john/
- Hash format list: `john --list=formats`
- rockyou.txt origin: leaked from RockYou data breach (2009), 14M real passwords
