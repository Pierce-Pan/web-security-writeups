# Lab: Username enumeration via different responses

## 1. Lab Information

- Platform: PortSwigger Web Security Academy
- Module: Authentication
- Difficulty: Apprentice
- Vulnerability Type: Username Enumeration
- Keywords: login error message, response difference, Burp Intruder, brute force

---

## 2. Vulnerability Background

Username enumeration occurs when an application reveals whether a username exists.

In this lab, the login function returns different error messages for an invalid username and an incorrect password. This allows an attacker to identify valid usernames first, then perform a more targeted password attack.

---

## 3. Testing Methodology

Start by sending login requests with different usernames and passwords.

Check whether the application returns different responses based on the username:

- Different error message
- Different status code
- Different response length
- Different response timing

---

## 4. Key Request

```http
POST /login HTTP/2
Host: vulnerable-site.web-security-academy.net
Cookie: session=[REDACTED]
Content-Type: application/x-www-form-urlencoded

username=test&password=123456
```

---

## 5. Exploitation Process

1. Capture a login request with Burp Suite.
2. Send the request to Intruder.
3. Mark the `username` value as the payload position.
4. Load the provided username list as payloads.
5. Start the attack and compare the responses.
6. Identify the username that produces a different error message.
7. Use the valid username to perform password testing.
8. Log in with the discovered credentials to complete the lab.

---

## 6. Root Cause

The application returned different error messages for different authentication failure cases.

This difference leaks whether a username exists in the system.

---

## 7. Remediation

- Use a generic login failure message such as `Invalid username or password`.
- Keep response status codes and response lengths as consistent as possible.
- Apply rate limiting to login attempts.
- Add account protection mechanisms and anomaly detection.
- Avoid exposing whether a username or email address is registered.

---

## 8. Summary

The key lesson is:

> Authentication failure messages should not reveal whether the username exists.
