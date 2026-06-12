# Gobuster Commands

## Directory Enumeration

```bash
gobuster dir \
-u http://target.local \
-w /usr/share/wordlists/dirb/common.txt
```

---

## Add File Extensions

```bash
gobuster dir \
-u http://target.local \
-w /usr/share/wordlists/dirb/common.txt \
-x php,html,txt
```

---

## Save Output

```bash
gobuster dir \
-u http://target.local \
-w /usr/share/wordlists/dirb/common.txt \
-o results.txt
```

---

## Show Status Codes

```bash
gobuster dir \
-u http://target.local \
-w /usr/share/wordlists/dirb/common.txt \
-s 200,301,302,403
```

---

## Exclude Status Codes

```bash
gobuster dir \
-u http://target.local \
-w /usr/share/wordlists/dirb/common.txt \
-b 404
```

---

## DNS Enumeration

```bash
gobuster dns \
-d example.com \
-w dns-wordlist.txt
```

---

## Virtual Host Enumeration

```bash
gobuster vhost \
-u http://target.local \
-w vhosts.txt
```

---

## Increase Threads

```bash
gobuster dir \
-u http://target.local \
-w wordlist.txt \
-t 50
```

---

## Show Help

```bash
gobuster -h
```
