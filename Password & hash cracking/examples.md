# John the Ripper — Experiments

> All experiments are done in `~/password-labs/john/` on your local Kali machine.

---

## Experiment 1 — Crack an MD5 hash

**Goal:** Understand how wordlist attacks work against MD5 hashes.

```bash
cd ~/password-labs/john

# Step 1: Create a hash
echo -n "password123" | md5sum | awk '{print $1}' > md5.txt
cat md5.txt    # verify hash is there

# Step 2: Crack it
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt md5.txt

# Step 3: Show result
john --show --format=raw-md5 md5.txt
```

**Expected output:** `?:password123`

**Try a stronger password:**
```bash
echo -n "X7#mQ!99" | md5sum | awk '{print $1}' > hard.txt
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hard.txt
john --show --format=raw-md5 hard.txt
```
Notice it won't crack — the password isn't in the wordlist.

---

## Experiment 2 — Crack SHA1 and SHA256

```bash
# SHA1
echo -n "hello" | sha1sum | awk '{print $1}' > sha1.txt
john --format=raw-sha1 --wordlist=/usr/share/wordlists/rockyou.txt sha1.txt
john --show --format=raw-sha1 sha1.txt

# SHA256
echo -n "letmein" | sha256sum | awk '{print $1}' > sha256.txt
john --format=raw-sha256 --wordlist=/usr/share/wordlists/rockyou.txt sha256.txt
john --show --format=raw-sha256 sha256.txt
```

**What to observe:** MD5, SHA1, SHA256 all crack just as fast — the algorithm speed doesn't protect weak passwords.

---

## Experiment 3 — Crack a Linux shadow-style hash

**Goal:** Simulate cracking a real Linux password file.

```bash
# Step 1: Generate a SHA-512 hash (Linux format)
openssl passwd -6 -salt mysalt "letmein"
# Copy the output hash e.g. $6$mysalt$xxxxx...

# Step 2: Create fake passwd and shadow files
echo "fakeuser:x:1001:1001::/home/fakeuser:/bin/bash" > passwd.txt
echo "fakeuser:PASTE_HASH_HERE:19000:0:99999:7:::" > shadow.txt

# Step 3: Combine with unshadow
unshadow passwd.txt shadow.txt > combined.txt

# Step 4: Crack
john --wordlist=/usr/share/wordlists/rockyou.txt combined.txt

# Step 5: Show result
john --show combined.txt
```

---

## Experiment 4 — Rule-based attack

**Goal:** Crack a password that's a wordlist word with mutations (e.g. `Password1!`).

```bash
echo -n "Password1!" | md5sum | awk '{print $1}' > mutated.txt
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt --rules mutated.txt
john --show --format=raw-md5 mutated.txt
```

Rules apply transformations like capitalizing, adding numbers, replacing letters with symbols.

---

## Experiment 5 — Crack multiple hashes at once

```bash
# Create 3 hashes in one file
echo -n "sunshine" | md5sum | awk '{print $1}' > multi.txt
echo -n "monkey"   | md5sum | awk '{print $1}' >> multi.txt
echo -n "abc123"   | md5sum | awk '{print $1}' >> multi.txt

# Crack all at once
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt multi.txt
john --show --format=raw-md5 multi.txt
```

---

## Results Log (fill this in as you practice)

| Hash | Password | Time to crack | Method |
|------|----------|---------------|--------|
| MD5 of "password123" | password123 | < 1 sec | Wordlist |
| MD5 of "X7#mQ!99" | Not cracked | — | Not in wordlist |
| SHA1 of "hello" | hello | < 1 sec | Wordlist |
| Linux shadow "letmein" | letmein | < 5 sec | Wordlist |
