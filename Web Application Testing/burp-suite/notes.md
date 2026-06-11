# Burp Suite Notes

## Key Concepts

### Request

A message sent from the client to the server.

Example:

```http
GET /index.html HTTP/1.1
```

---

### Response

A message returned by the server.

Example:

```http
HTTP/1.1 200 OK
```

---

### Headers

Metadata associated with requests and responses.

Examples:

```http
Host:
Cookie:
User-Agent:
Content-Type:
```

---

### Parameters

Values supplied by users.

Examples:

```text
?id=10
?page=home
```

---

### Cookies

Used to maintain session state.

Example:

```http
Cookie: sessionid=123456
```

---

## Most Important Tabs

### Proxy

Captures traffic.

### HTTP History

Records all requests and responses.

### Target

Maps application structure.

### Repeater

Manual testing and experimentation.

### Decoder

Data conversion.

---

## Beginner Workflow

```text
Open Browser
      ↓
Browse Website
      ↓
Inspect Requests
      ↓
Review Responses
      ↓
Explore Site Map
      ↓
Send Requests to Repeater
      ↓
Document Findings
```

---

## Common Mistakes

- Leaving interception enabled accidentally
- Ignoring response headers
- Not documenting findings
- Testing without understanding the request

---

## Personal Notes

- Burp is best learned by exploring HTTP traffic.
- Spend time understanding requests before using automation.
- Learn how cookies work.
- Learn session management concepts.
- Use Repeater frequently to understand application behavior.
