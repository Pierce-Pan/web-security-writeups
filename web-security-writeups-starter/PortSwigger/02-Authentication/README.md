# Authentication Labs

Authentication vulnerabilities happen when an application fails to correctly verify user identity or protect the login process.

This section focuses on:

- Username enumeration
- Brute-force protection bypass
- MFA / 2FA logic flaws
- Remember-me cookie weaknesses
- Password reset vulnerabilities
- Password change workflow flaws

---

## Recommended Important Labs

| Priority | Lab | Vulnerability Type | Why It Matters |
|---|---|---|---|
| P0 | Username enumeration via different responses | Username enumeration | Basic but very common |
| P0 | Username enumeration via subtly different responses | Username enumeration | Shows attention to detail |
| P0 | Username enumeration via response timing | Timing side channel | More technical and valuable |
| P0 | Broken brute-force protection, IP block | Brute-force bypass | Common weak defense design |
| P0 | Username enumeration via account lock | Account lock side channel | Defense mechanism leaks information |
| P0 | 2FA simple bypass | MFA bypass | Direct authentication flow bypass |
| P0 | 2FA broken logic | MFA logic flaw | Token not correctly bound to user/session |
| P0 | Brute-forcing a stay-logged-in cookie | Weak remember-me token | Cookie design and hash cracking |
| P0 | Offline password cracking | Cookie leakage + cracking | Good combined vulnerability example |
| P0 | Password reset broken logic | Password reset flaw | High real-world impact |
| P0 | Basic password reset poisoning | Host header attack | Valuable real-world web security topic |
| P0 | Password reset poisoning via middleware | Header-based reset poisoning | Advanced Host/X-Forwarded-Host case |
| P0 | Password brute-force via password change | Password change logic flaw | Business logic and authentication combined |
