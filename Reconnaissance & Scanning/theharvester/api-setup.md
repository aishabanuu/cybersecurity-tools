# API Setup

## Why API Keys?

Many OSINT providers limit anonymous access.

API keys allow theHarvester to access additional data sources.

Common services requiring API keys:

- Shodan
- Censys
- SecurityTrails
- Hunter.io
- Intelligence X
- VirusTotal

---

## API Key Location

Configuration file:

```bash
~/.theHarvester/api-keys.yaml
```

Open file:

```bash
nano ~/.theHarvester/api-keys.yaml
```

---

## Example Configuration

```yaml
shodan:
  key: YOUR_SHODAN_API_KEY

hunter:
  key: YOUR_HUNTER_API_KEY

censys:
  id: YOUR_CENSYS_ID
  secret: YOUR_CENSYS_SECRET
```

---

## Verify Configuration

Run:

```bash
theHarvester -l
```

Then test a source:

```bash
theHarvester -d example.com -b shodan
```

---

## Security Notes

Never commit API keys to GitHub.

Add to `.gitignore`:

```gitignore
api-keys.yaml
.env
```

Store credentials securely and rotate them when necessary.
