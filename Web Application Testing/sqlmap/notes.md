# SQLMap Notes

## What is SQL Injection?

SQL Injection occurs when an application improperly handles user input and passes it directly to a database query.

The result can be:

- Unexpected application behavior
- Data exposure
- Unauthorized actions
- Database compromise

Understanding the concept is important even when using automated tools.

---

## Databases Commonly Encountered

| Database | Description |
|-----------|-------------|
| MySQL | Popular open-source database |
| PostgreSQL | Advanced open-source database |
| MSSQL | Microsoft SQL Server |
| Oracle | Enterprise database platform |
| SQLite | Lightweight embedded database |
| MariaDB | MySQL-compatible database |

---

## Key Concepts

### Parameters

Values supplied by users.

Examples:

```text
?id=1
?page=home
?product=10
```

Parameters are common assessment targets.

---

### Cookies

Applications often use cookies to track sessions.

Example:

```http
Cookie: SESSIONID=abc123
```

Understanding session management is essential during testing.

---

### Request Files

Captured HTTP requests can be saved and analyzed.

Example:

```text
request.txt
```

This allows detailed examination of application behavior.

---

## Understanding Results

Assessment results may include:

### Parameter Information

Which parameter was tested.

### Database Identification

Which database technology appears to be in use.

### Response Analysis

How the application responded to test requests.

---

## Typical Learning Workflow

```text
Understand HTTP
        ↓
Learn Parameters
        ↓
Capture Requests
        ↓
Analyze Inputs
        ↓
Review Results
        ↓
Document Findings
```

---

## Relationship to Other Tools

| Tool | Purpose |
|--------|---------|
| Burp Suite | Capture and inspect requests |
| Gobuster | Discover content |
| Nikto | Assess server configuration |
| SQLMap | Analyze database-related input handling |
| Nmap | Network and service discovery |

---

## Common Mistakes

- Testing systems without authorization
- Ignoring application context
- Focusing only on tools instead of concepts
- Not documenting findings
- Failing to understand HTTP requests

---

## Personal Notes

- Learn HTTP before learning automation.
- Understand parameters and cookies.
- Capture requests with Burp Suite first.
- Review assessment results carefully.
- Use lab environments for practice.
- Focus on learning application behavior and secure development concepts.
