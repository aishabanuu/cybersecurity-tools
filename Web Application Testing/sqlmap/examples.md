# SQLMap Examples

## Example 1: Analyze a URL Parameter

Application URL:

```text
http://localhost/product?id=1
```

Assessment:

```bash
sqlmap -u "http://localhost/product?id=1"
```

Purpose:

- Analyze parameter handling
- Learn how applications process user input

---

## Example 2: Review Output

Example Findings:

```text
Parameter: id
Type: Integer
Backend DBMS: MySQL
```

Purpose:

- Understand assessment results
- Identify technologies in use

---

## Example 3: Use a Captured Request

Capture traffic with Burp Suite.

Save request as:

```text
request.txt
```

Analyze:

```bash
sqlmap -r request.txt
```

Purpose:

- Study real application requests
- Understand request structure

---

## Example 4: Authenticated Testing

Example:

```bash
sqlmap -u "http://localhost/profile?id=1" \
--cookie="SESSIONID=abc123"
```

Purpose:

- Assess authenticated application functionality
- Understand session handling

---

## Example 5: Save Assessment Results

```bash
sqlmap -u "http://localhost/product?id=1" \
--output-dir=results
```

Output:

```text
results/
```

Useful for reporting and documentation.
