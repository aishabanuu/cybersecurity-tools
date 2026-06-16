# theHarvester Notes

## What is OSINT?

OSINT (Open Source Intelligence) is information gathered from publicly available sources.

Examples:

- Search engines
- DNS records
- Public repositories
- Security search engines
- Public documents

theHarvester is primarily an OSINT collection tool.

---

## Key Concepts

### Domain

A target organization or website.

Example:

```text
example.com
```

---

### Subdomain

A subdivision of a domain.

Examples:

```text
mail.example.com
vpn.example.com
api.example.com
```

Subdomains often reveal additional infrastructure.

---

### Email Enumeration

Publicly exposed email addresses can help identify:

- Departments
- Naming conventions
- Contact points

Example:

```text
admin@example.com
support@example.com
```

---

### Host Discovery

theHarvester may identify:

```text
vpn.example.com
mail.example.com
portal.example.com
```

These findings help map external assets.

---

## Common Sources

| Source | Purpose |
|----------|----------|
| Bing | Search engine results |
| DuckDuckGo | Search engine results |
| Brave | Search engine results |
| Shodan | Internet-connected devices |
| Censys | Internet infrastructure |
| SecurityTrails | DNS and subdomain data |
| VirusTotal | Security intelligence |
| Hunter.io | Email discovery |

---

## Typical Recon Workflow

```text
Whois
   ↓
Dig
   ↓
theHarvester
   ↓
Subdomain Collection
   ↓
Host Identification
   ↓
Documentation
```

---

## Common Mistakes

- Assuming all results are accurate
- Failing to verify findings
- Ignoring duplicate entries
- Exposing API keys in repositories
- Not documenting discovered assets

---

## Personal Notes

- Start with free sources.
- Verify findings manually.
- Keep API keys secure.
- Save reports for later review.
- Compare results from multiple sources.
- Use findings to support later reconnaissance activities.
