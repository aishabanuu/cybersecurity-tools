# Whois Examples

## Example 1: Domain Lookup

Command:

```bash
whois example.com
```

Sample Output:

```text
Domain Name: EXAMPLE.COM

Registrar: Example Registrar

Creation Date: 1995-08-14

Registry Expiry Date: 2030-08-13

Name Server: NS1.EXAMPLE.COM

Name Server: NS2.EXAMPLE.COM
```

---

## Example 2: Investigating a Company Domain

Command:

```bash
whois company.com
```

Useful Information:

- Registrar
- Domain age
- Nameservers
- Registration status

Questions to Ask:

- Is the domain newly registered?
- Which registrar is being used?
- Are there unusual nameservers?

---

## Example 3: IP Address Ownership

Command:

```bash
whois 8.8.8.8
```

Sample Output:

```text
Organization: Google LLC

NetRange: 8.8.8.0 - 8.8.8.255

Country: US
```

Purpose:

- Identify hosting providers
- Determine ownership
- Investigate infrastructure

---

## Example 4: Discover Nameservers

Command:

```bash
whois example.com | grep "Name Server"
```

Output:

```text
Name Server: NS1.EXAMPLE.COM

Name Server: NS2.EXAMPLE.COM
```

This information can support DNS reconnaissance.

---

## Example 5: Domain Age Analysis

Command:

```bash
whois example.com | grep Creation
```

Output:

```text
Creation Date: 1995-08-14
```

Older domains are often more established, while recently registered domains may require additional scrutiny.
