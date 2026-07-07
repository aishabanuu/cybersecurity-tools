# 🧪 Hashcat — Experiments

> All experiments done in `~/password-labs/hashcat/` on your local Kali machine.

---

## Experiment 1 — Crack multiple MD5 hashes

```bash
cd ~/password-labs/hashcat

# Step 1: Create 3 hashes
echo -n "sunshine" | md5sum | awk '{print $1}' > hashes.txt
echo -n "monkey"   | md5sum | awk '{print $1}' >> hashes.txt
echo -n "abc123"   | md5sum | awk '{print $1}' >> hashes.txt
cat hashes.txt    # verify 3 hashes

# Step 2: Crack them all
hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt --force

# Step 3: Show results
hashcat -m 0 hashes.txt --show
```

---

## Experiment 2 — Brute force a 4-digit PIN

```bash
# Step 1: Create hash of a PIN
echo -n "2847" | md5sum | awk '{print $1}' > pin.txt

# Step 2: Brute force all 4-digit combos
hashcat -m 0 -a 3 pin.txt ?d?d?d?d --force

# Step 3: Show result
hashcat -m 0 pin.txt --show
```

**What to observe:** 4-digit PINs have only 10,000 combinations — cracks almost instantly.

---

## Experiment 3 — Rule-based attack

```bash
# Step 1: Create hash of a mutated word
echo -n "Password1!" | md5sum | awk '{print $1}' > mutated.txt

# Step 2: Try plain wordlist first (will fail)
hashcat -m 0 -a 0 mutated.txt /usr/share/wordlists/rockyou.txt --force
hashcat -m 0 mutated.txt --show    # probably empty

# Step 3: Try with rules
hashcat -m 0 -a 0 mutated.txt /usr/share/wordlists/rockyou.txt \
  -r /usr/share/hashcat/rules/best64.rule --force
hashcat -m 0 mutated.txt --show
```

---

## Experiment 4 — Crack SHA256

```bash
echo -n "letmein" | sha256sum | awk '{print $1}' > sha256.txt
hashcat -m 1400 -a 0 sha256.txt /usr/share/wordlists/rockyou.txt --force
hashcat -m 1400 sha256.txt --show
```

---

## Experiment 5 — Try an uncrackable password

```bash
echo -n "T#9xQ!mZ2@kL" | md5sum | awk '{print $1}' > strong.txt
hashcat -m 0 -a 0 strong.txt /usr/share/wordlists/rockyou.txt --force
hashcat -m 0 strong.txt --show    # nothing — not in any wordlist
```

**Lesson:** Random passwords not based on words are effectively immune to wordlist attacks.

---

## Results Log

| Experiment | Hash Type | Password | Cracked? | Method | Time |
|------------|-----------|----------|----------|--------|------|
| 1 — sunshine | MD5 | sunshine | ✅ | Wordlist | < 1s |
| 2 — PIN | MD5 | 2847 | ✅ | Brute force | < 1s |
| 3 — Password1! | MD5 | Password1! | ✅ | Rules | ~5s |
| 5 — Random | MD5 | T#9xQ!mZ2@kL | ❌ | Wordlist | — |
