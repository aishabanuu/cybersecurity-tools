# theHarvester Commands

## Display Help

```bash
theHarvester -h
```

---

## Display Available Sources

```bash
theHarvester -l
```

---

## Basic Domain Search

```bash
theHarvester -d example.com -b bing
```

---

## Search Using All Sources

```bash
theHarvester -d example.com -b all
```

---

## Search Using Brave

```bash
theHarvester -d example.com -b brave
```

---

## Search Using DuckDuckGo

```bash
theHarvester -d example.com -b duckduckgo
```

---

## Save Results

```bash
theHarvester -d example.com -b all -f report
```

Output Files:

```text
report.html
report.xml
```

---

## Limit Number of Results

```bash
theHarvester -d example.com -b bing -l 100
```

---

## Search for Emails and Hosts

```bash
theHarvester -d example.com -b all
```

Typical Output:

```text
Emails Found
Hosts Found
IPs Found
```

---

## Check Version

```bash
theHarvester --version
```
