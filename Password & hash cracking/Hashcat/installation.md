# 🔧 Hashcat — Installation

## Step 1 — Check if already installed
```bash
hashcat --version
```
Expected: `v6.x.x` or later. If you see this, skip to Step 3.

---

## Step 2 — Install (if missing)
```bash
sudo apt update
sudo apt install hashcat -y
hashcat --version    # verify
```

---

## Step 3 — VM note (important)
Hashcat is GPU-accelerated. Inside a VM (VirtualBox/VMware), the GPU isn't available,
so you **must** add `--force` to all commands to run in CPU mode:
```bash
hashcat -m 0 -a 0 hash.txt wordlist.txt --force
```
Without `--force` inside a VM, hashcat will error out.

---

## Step 4 — Prepare rockyou wordlist
```bash
sudo gunzip /usr/share/wordlists/rockyou.txt.gz   # if still zipped
wc -l /usr/share/wordlists/rockyou.txt             # confirm 14M+ lines
```

---

## Step 5 — Create working directory
```bash
mkdir ~/password-labs/hashcat
cd ~/password-labs/hashcat
```

---

## Step 6 — Sanity test
```bash
echo -n "password" | md5sum | awk '{print $1}' > test.txt
hashcat -m 0 -a 0 test.txt /usr/share/wordlists/rockyou.txt --force
hashcat -m 0 test.txt --show
```
✅ You should see `<hash>:password` in the output.

---

## Where Hashcat Stores Results

Cracked hashes are saved to:
```bash
~/.local/share/hashcat/hashcat.potfile
cat ~/.local/share/hashcat/hashcat.potfile
```
