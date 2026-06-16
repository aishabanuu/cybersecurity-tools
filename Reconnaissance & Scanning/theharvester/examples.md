# theHarvester Examples

## Example 1: Basic Domain Enumeration

Command:

```bash
theHarvester -d example.com -b bing
```

Possible Results:

```text
Hosts Found:
mail.example.com
vpn.example.com

Emails Found:
admin@example.com
support@example.com
```

Purpose:

- Discover infrastructure
- Identify public contact information

---

## Example 2: Use Multiple Sources

Command:

```bash
theHarvester -d example.com -b all
```

Purpose:

- Collect broader results
- Compare findings across sources

---

## Example 3: Save Report

Command:

```bash
theHarvester -d example.com -b all -f company-report
```

Generated Files:

```text
company-report.html
company-report.xml
```

Purpose:

- Documentation
- Reporting
- Future analysis

---

## Example 4: Discover Subdomains

Command:

```bash
theHarvester -d example.com -b crtsh
```

Possible Output:

```text
api.example.com
vpn.example.com
mail.example.com
dev.example.com
```

Purpose:

- Asset discovery
- Infrastructure mapping

---

## Example 5: Query a Single Source

Command:

```bash
theHarvester -d example.com -b duckduckgo
```

Purpose:

- Quick reconnaissance
- Testing source availability
