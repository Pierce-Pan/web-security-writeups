# Web Security Writeups

[中文](./README.zh-CN.md) | **English**

This repository records my web security learning notes and lab writeups.

The current focus is **PortSwigger Web Security Academy**. Later, this repository will also include notes from **TryHackMe**, **HackTheBox**, **CTFHub**, and other CTF practice platforms.

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
- CTF web challenge writeups
- Real-world vulnerability analysis and remediation notes

---

## Repository Structure

```text
web-security-writeups/
├── README.md
├── README.zh-CN.md
├── writeup-template.en.md
├── writeup-template.zh-CN.md
├── PortSwigger/
│   ├── README.md
│   ├── README.zh-CN.md
│   ├── 01-Access-Control/
│   │   ├── README.md
│   │   ├── README.zh-CN.md
│   │   ├── 01-user-role-can-be-modified-in-user-profile.en.md
│   │   └── 01-user-role-can-be-modified-in-user-profile.zh-CN.md
│   └── 02-Authentication/
│       ├── README.md
│       ├── README.zh-CN.md
│       ├── 01-username-enumeration-via-different-responses.en.md
│       └── 01-username-enumeration-via-different-responses.zh-CN.md
├── TryHackMe/
├── HackTheBox/
├── CTFHub/
├── CTF/
└── assets/
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

## Sensitive Information

Before publishing, remove or redact:

- Real cookies
- Real session values
- Real passwords
- Real emails or phone numbers
- Private target information
- Unauthorized testing details

Example:

```http
Cookie: session=[REDACTED]
```

---

## Disclaimer

This repository is for educational purposes only. All writeups are based on legal labs, intentionally vulnerable environments, and authorized practice platforms.
