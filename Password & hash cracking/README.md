# 🔐 Password & Hash Cracking — Testing Password Security

> Notes, experiments, and tool references for understanding how passwords are cracked
> and how to defend against it. All practice done in legal, isolated lab environments.

---

## 📌 What is Password Cracking?

Password cracking is the process of recovering passwords from stored hashes.
Systems never store your actual password — they store a **hash** (a fixed-length fingerprint).
When you log in, the system hashes what you type and compares it to the stored hash.

**Cracking techniques:**

| Technique | Description |
|-----------|-------------|
| Wordlist attack | Try every word in a pre-built list (e.g. rockyou.txt) |
| Brute force | Try every possible combination of characters |
| Rule-based | Apply mutations to wordlist entries (e.g. `password` → `P@ssw0rd`) |
| Rainbow table | Use precomputed hash→password lookup tables |
| Online brute force | Directly attack a live login service (SSH, FTP, web form) |

---

## 🧰 Tools Covered

| Tool | Type | Best For |
|------|------|----------|
| [John the Ripper](./john-the-ripper/) | Offline cracker | Hash cracking, CTFs, shadow files |
| [Hashcat](./hashcat/) | Offline cracker (GPU) | Fast large-scale cracking |
| [Hydra](./hydra/) | Online brute-forcer | SSH, FTP, login form attacks |

---

## 🗂️ Folder Structure

```
password-hash-cracking/
│
├── README.md                  ← You are here
│
├── john-the-ripper/
│   ├── README.md
│   ├── installation.md
│   ├── commands.md
│   ├── examples.md
│   └── notes.md
│
├── hashcat/
│   ├── README.md
│   ├── installation.md
│   ├── commands.md
│   ├── examples.md
│   └── notes.md
│
└── hydra/
    ├── README.md
    ├── installation.md
    ├── commands.md
    ├── examples.md
    └── notes.md
```

---

## ⚙️ Lab Setup (Do This First)

### 1. Update Kali
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Unzip the rockyou wordlist
```bash
sudo gunzip /usr/share/wordlists/rockyou.txt.gz
wc -l /usr/share/wordlists/rockyou.txt   # should show 14M+ lines
```

### 3. Create a working folder
```bash
mkdir ~/password-labs
cd ~/password-labs
```

### 4. Install tools (if missing)
```bash
sudo apt install john hashcat hydra -y
```

### 5. Set up Metasploitable2 (for Hydra)
- Download from: https://sourceforge.net/projects/metasploitable/
- Run in VirtualBox/VMware on **Host-Only** network
- Default credentials: `msfadmin / msfadmin`
- Find its IP: `sudo netdiscover -r 192.168.56.0/24`

---

## 🔑 Common Hash Types

| Hash | Example | Length |
|------|---------|--------|
| MD5 | `5f4dcc3b5aa765d61d8327deb882cf99` | 32 chars |
| SHA1 | `5baa61e4c9b93f3f0682250b6cf8331b7ee68fd8` | 40 chars |
| SHA256 | `6b86b273ff34fce19d6b804eff5a3f5747ada4eaa22f1d49c01e52ddb7875b4b` | 64 chars |
| SHA512 | `$6$...` | 128 chars |
| NTLM | Windows password hash | 32 chars |
| bcrypt | `$2b$...` | 60 chars |

> **Tip:** Use [hash-identifier](https://github.com/blackploit/hash-identifier) or `hashid` to identify unknown hashes.
> ```bash
> hashid <paste_hash_here>
> ```

---

## 🛡️ Defensive Takeaways

- Never store passwords as plain MD5 or SHA1 — use **bcrypt**, **Argon2**, or **scrypt**
- Always use **salting** to prevent rainbow table attacks
- Enforce **strong password policies** (length > complexity)
- Use **rate limiting** and **account lockout** to stop online brute force
- Enable **multi-factor authentication (MFA)**

---

## ⚠️ Disclaimer

All experiments are performed on **personal VMs and intentionally vulnerable machines**
(Metasploitable2, local hashes). Never attempt these techniques on systems you do not
own or have explicit written permission to test.

---

*Last updated: June 2026*
