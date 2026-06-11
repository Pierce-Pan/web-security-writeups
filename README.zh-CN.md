# Web Security Writeups

**中文** | [English](./README.md)

本仓库用于记录我的 Web 安全学习笔记、靶场练习过程和漏洞分析 writeup。

当前主要内容是 **PortSwigger Web Security Academy**。后续会逐步扩展到 **TryHackMe**、**HackTheBox**、**CTFHub** 以及其他 CTF Web 题目。

> 本仓库内容仅用于合法安全学习、靶场练习和防御研究。

---

## 当前学习重点

### PortSwigger Web Security Academy

- Access Control / 访问控制
- Authentication / 身份认证
- SQL Injection / SQL 注入
- Cross-site Scripting / XSS
- Server-side Request Forgery / SSRF
- File Upload Vulnerabilities / 文件上传漏洞
- Business Logic Vulnerabilities / 业务逻辑漏洞

### 后续计划

- TryHackMe Web 安全房间
- HackTheBox 靶机与 Web Challenge
- CTFHub Web 方向题目
- CTF 比赛 Web 题 writeup
- 真实漏洞复现与修复分析笔记

---

## 仓库目录结构

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

## Writeup 写作结构

每篇 writeup 建议包含以下内容：

1. Lab 基本信息
2. 漏洞背景
3. 测试思路
4. 关键请求与响应
5. 利用过程
6. 漏洞根因
7. 修复建议
8. 总结

本仓库不追求单纯记录“答案”，而是重点展示：

- 如何发现漏洞
- 如何验证漏洞
- 如何使用 Burp Suite 辅助测试
- 漏洞为什么会产生
- 如何从开发和防御角度修复漏洞

---

## 敏感信息处理

上传前必须删除或打码以下内容：

- 真实 Cookie
- 真实 Session
- 真实密码
- 真实邮箱、手机号
- 个人隐私信息
- 未授权目标信息
- 真实业务系统漏洞细节

示例：

```http
Cookie: session=[REDACTED]
```

---

## Disclaimer

本仓库仅用于安全学习和防御研究。所有内容均来自合法靶场、授权练习环境或公开 CTF 题目。
