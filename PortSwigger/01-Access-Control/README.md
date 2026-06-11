# Access Control Labs

[中文](./README.zh-CN.md) | **English**

Access control vulnerabilities happen when users can perform actions or access resources outside their intended permissions.

This section focuses on:

- Vertical privilege escalation
- Horizontal privilege escalation
- IDOR
- Header-based access control bypass
- Method-based access control bypass
- Multi-step process authorization flaws

---

## Recommended Important Labs

| Priority | Lab | Vulnerability Type | Why It Matters |
|---|---|---|---|
| P0 | Insecure direct object references | IDOR | Very common in real business systems |
| P0 | User ID controlled by request parameter | Horizontal privilege escalation | Classic object-level authorization failure |
| P0 | User ID controlled by request parameter with password disclosure | IDOR + sensitive data exposure | Clear real-world impact |
| P0 | User ID controlled by request parameter with data leakage in redirect | Data leakage during redirect | Shows the importance of checking full responses |
| P0 | User role controlled by request parameter | Vertical privilege escalation | Client-controlled privilege parameter |
| P0 | User role can be modified in user profile | Broken access control | Hidden sensitive field accepted by backend |
| P0 | URL-based access control can be circumvented | Header bypass | Reverse proxy or routing-based bypass |
| P0 | Method-based access control can be circumvented | HTTP method bypass | Common configuration mistake |
| P0 | Multi-step process with no access control on one step | Business logic access control flaw | Very relevant to real applications |
| P0 | Referer-based access control | Header-based access control flaw | Referer header is user-controllable |

---

## Suggested Writing Order

1. IDOR static file / transcript
2. User ID controlled by request parameter
3. User ID with password disclosure
4. User ID data leakage in redirect
5. User role controlled by request parameter
6. User role modified in profile
7. URL-based access control bypass
8. Method-based access control bypass
9. Multi-step process missing access control
10. Referer-based access control
