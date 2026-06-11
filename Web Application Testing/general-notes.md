# General Notes

## What is Web Application Testing?

Web application testing is the process of evaluating a web application for security weaknesses, misconfigurations, and design flaws.

The goal is to identify issues before attackers can exploit them.

---

## Common Components

### Client Side

Runs in the browser.

Examples:

- HTML
- CSS
- JavaScript

### Server Side

Processes requests and generates responses.

Examples:

- PHP
- Python
- Java
- Node.js

### Database

Stores application data.

Examples:

- MySQL
- PostgreSQL
- MSSQL

---

## HTTP Methods

### GET

Requests data.

Example:

```http
GET /products?id=1 HTTP/1.1
```

### POST

Sends data to the server.

Example:

```http
POST /login HTTP/1.1
```

### PUT

Updates data.

### DELETE

Removes data.

---

## HTTP Status Codes

| Code | Meaning |
|--------|----------|
| 200 | OK |
| 301 | Redirect |
| 302 | Temporary Redirect |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

## Common Vulnerability Categories

### Authentication Issues

Weak login mechanisms.

### Authorization Issues

Users accessing resources they should not.

### Input Validation Problems

Improper handling of user input.

### Security Misconfigurations

Default credentials, exposed files, weak settings.

### Sensitive Data Exposure

Improper protection of confidential information.

---

## Typical Workflow

```text
Reconnaissance
      ↓
Content Discovery
      ↓
Application Mapping
      ↓
Input Testing
      ↓
Configuration Review
      ↓
Documentation
```

---

## Documentation Tips

Always record:

- Target scope
- Commands used
- Findings
- Screenshots
- Remediation recommendations

---

## Personal Notes

- Understand HTTP before learning tools.
- Learn manual testing first.
- Keep detailed notes.
- Practice in lab environments.
- Focus on understanding findings rather than collecting them.
