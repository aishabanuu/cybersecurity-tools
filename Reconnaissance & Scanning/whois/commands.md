# Whois Commands

## Basic Domain Lookup

```bash
whois example.com
```

---

## Lookup an IP Address

```bash
whois 8.8.8.8
```

---

## Save Results to File

```bash
whois example.com > whois-output.txt
```

---

## Search for Nameservers

```bash
whois example.com | grep "Name Server"
```

---

## Search for Registrar

```bash
whois example.com | grep Registrar
```

---

## Search for Expiration Date

```bash
whois example.com | grep Expiry
```

---

## Search for Creation Date

```bash
whois example.com | grep Creation
```

---

## Query an ASN

```bash
whois AS15169
```

---

## View Complete Record

```bash
whois example.com | less
```

---

## Extract Important Fields

```bash
whois example.com | egrep "Registrar|Creation|Expiry|Name Server"
```
