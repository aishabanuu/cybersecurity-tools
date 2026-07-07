# 🔧 John the Ripper — Installation

## Step 1 — Check if already installed
```bash
john --version
```
Expected output: `John the Ripper 1.9.x ...`
If you see this, skip to Step 3.

---

## Step 2 — Install (if missing)
```bash
sudo apt update
sudo apt install john -y
```

Verify after install:
```bash
john --version
which john        # should return /usr/sbin/john
```

---

## Step 3 — Prepare the rockyou wordlist
```bash
# Check if it exists
ls /usr/share/wordlists/

# Unzip if it's still compressed
sudo gunzip /usr/share/wordlists/rockyou.txt.gz

# Confirm line count (should be 14M+)
wc -l /usr/share/wordlists/rockyou.txt
```

---

## Step 4 — Create your working directory
```bash
mkdir ~/password-labs/john
cd ~/password-labs/john
```

---

## Step 5 — Sanity test
```bash
echo -n "password123" | md5sum | awk '{print $1}' > test.txt
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt test.txt
john --show --format=raw-md5 test.txt
```

✅ If you see `password123` in the output — John is working correctly.

---

## Optional: Install John the Ripper Jumbo (more formats)
```bash
sudo apt install john-jumbo -y
```
Jumbo version supports more hash types including bcrypt, ZIP, PDF passwords, etc.
