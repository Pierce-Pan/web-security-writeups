# Web Security Writeups

This repository records my web security learning notes and lab writeups.

The current focus is **PortSwigger Web Security Academy**, especially **Access Control** and **Authentication** labs. Later, this repository will also include notes from **TryHackMe**, **HackTheBox**, **CTFHub**, and other CTF practice platforms.

> All content is for legal security learning, lab practice, and defensive research only.

---

## Current Focus

### PortSwigger Web Security Academy

- Access Control
- Authentication
- SQL Injection
- Cross-site Scripting
- Server-side Request Forgery
- File Upload Vulnerabilities
- Business Logic Vulnerabilities

### Future Plan

- TryHackMe web security rooms
- HackTheBox machines and challenges
- CTFHub web challenges
- Real-world vulnerability analysis and remediation notes

---

## Repository Structure

```text
web-security-writeups/
├── README.md
├── writeup-template.md
├── PortSwigger/
│   ├── README.md
│   ├── 01-Access-Control/
│   │   ├── README.md
│   │   └── 01-user-role-can-be-modified-in-user-profile.md
│   └── 02-Authentication/
│       ├── README.md
│       └── 01-username-enumeration-via-different-responses.md
├── TryHackMe/
│   └── README.md
├── HackTheBox/
│   └── README.md
├── CTF/
│   └── README.md
└── assets/
    └── README.md
```

---

## Writeup Format

Each writeup should include:

1. Lab information
2. Vulnerability background
3. Testing methodology
4. Key request and response
5. Exploitation process
6. Root cause
7. Remediation
8. Summary

The goal is not only to show the final answer, but also to demonstrate the security testing process and the reasoning behind it.

---

## Notes

Sensitive information must be removed before publishing:

- Real cookies
- Real session values
- Real passwords
- Real emails or phone numbers
- Private targets
- Unauthorized testing details

Use placeholders such as:

```http
Cookie: session=[REDACTED]
```

---

## Disclaimer

This repository is for educational purposes only. All writeups are based on legal labs, intentionally vulnerable environments, and authorized practice platforms.
