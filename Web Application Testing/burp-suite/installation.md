# Burp Suite Installation

## Verify Installation

Kali Linux usually includes Burp Suite.

Check:

```bash
burpsuite --version
```

---

## Launch Burp Suite

Terminal:

```bash
burpsuite
```

or

```text
Applications
→ Web Application Analysis
→ Burp Suite
```

---

## First Launch

Select:

```text
Temporary Project
```

Click:

```text
Next
```

Choose:

```text
Use Burp Defaults
```

Click:

```text
Start Burp
```

---

## Verify Proxy Listener

Navigate to:

```text
Proxy → Options
```

Default Listener:

```text
127.0.0.1:8080
```

---

## Built-in Browser

Open:

```text
Proxy → Intercept → Open Browser
```

Using the built-in browser is recommended for beginners because proxy settings are already configured.
