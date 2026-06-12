# Gobuster Examples

## Example 1: Discover Directories

Command:

```bash
gobuster dir \
-u http://localhost \
-w /usr/share/wordlists/dirb/common.txt
```

Output:

```text
/admin
/images
/uploads
/css
/js
```

Purpose:

- Identify hidden content
- Map application structure

---

## Example 2: Find PHP Files

Command:

```bash
gobuster dir \
-u http://localhost \
-w /usr/share/wordlists/dirb/common.txt \
-x php
```

Output:

```text
/login.php
/admin.php
/config.php
```

Purpose:

- Identify application entry points
- Discover administrative interfaces

---

## Example 3: Save Results

Command:

```bash
gobuster dir \
-u http://localhost \
-w /usr/share/wordlists/dirb/common.txt \
-o gobuster-results.txt
```

Output:

```text
gobuster-results.txt
```

Useful for documentation and reporting.

---

## Example 4: Virtual Host Discovery

Command:

```bash
gobuster vhost \
-u http://target.local \
-w vhosts.txt
```

Possible Results:

```text
admin.target.local
dev.target.local
api.target.local
```

Purpose:

- Identify hidden services
- Expand attack surface understanding

---

## Example 5: DNS Enumeration

Command:

```bash
gobuster dns \
-d example.com \
-w subdomains.txt
```

Output:

```text
api.example.com
mail.example.com
vpn.example.com
```

Purpose:

- Discover additional infrastructure
- Expand reconnaissance scope
