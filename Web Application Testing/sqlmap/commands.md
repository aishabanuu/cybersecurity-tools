# SQLMap Commands

## Display Help

```bash
sqlmap -h
```

---

## Display Version

```bash
sqlmap --version
```

---

## Test a URL Parameter

```bash
sqlmap -u "http://localhost/page?id=1"
```

Purpose:

- Analyze URL parameters
- Identify possible injection points

---

## Increase Verbosity

```bash
sqlmap -u "http://localhost/page?id=1" -v 3
```

Useful for learning and understanding assessment activity.

---

## Specify a Request File

```bash
sqlmap -r request.txt
```

Purpose:

- Analyze captured HTTP requests

---

## Specify Cookies

```bash
sqlmap -u "http://localhost/page?id=1" \
--cookie="SESSIONID=value"
```

Useful for authenticated testing in authorized labs.

---

## Save Output

```bash
sqlmap -u "http://localhost/page?id=1" \
--output-dir=results
```

Store assessment results for documentation.

---

## Batch Mode

```bash
sqlmap -u "http://localhost/page?id=1" --batch
```

Automatically selects default answers.

Useful when reviewing assessment workflows.

---

## List Available Options

```bash
sqlmap --help
```
