---
# Security Scan Output: Example Web App

## Overview
- Target: example.com (test environment)
- Tool: OWASP ZAP 2.14.0
- Date: 2025-06-20
- Purpose: Demonstrate common automated scan findings
- Scan source: local container with default ruleset
---

## Sample Findings
```
Alert: SQL Injection
Risk: High
URL: https://example.com/login
Parameter: username
Evidence: sql syntax error near 'OR 1=1'

Alert: Server Leaks Version Information
Risk: Medium
URL: https://example.com/
Evidence: Server: Apache/2.4.52 (Ubuntu)

Alert: Cookie No HttpOnly Flag
Risk: Low
Set-Cookie: sessionid=abc123; Path=/; Secure

Alert: Reflected Cross-Site Scripting
Risk: High
URL: https://example.com/search
Parameter: q
Evidence: <script>alert(1)</script>

Alert: Outdated JavaScript Library
Risk: Medium
URL: https://example.com/static/app.js
Evidence: jQuery 1.8.3 detected

Alert: Missing Content-Security-Policy Header
Risk: Low
URL: https://example.com/
```

### Next Steps
1. Sanitize all user input in the login form.
2. Disable unnecessary server banners.
3. Enable the `HttpOnly` flag on authentication cookies.
4. Update third-party libraries and add a Content Security Policy header.
