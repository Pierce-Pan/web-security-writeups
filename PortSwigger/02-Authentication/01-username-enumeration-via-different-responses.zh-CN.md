# Lab: Username enumeration via different responses

**中文** | [English](./01-username-enumeration-via-different-responses.en.md)

## 1. Lab 基本信息

- 平台：PortSwigger Web Security Academy
- 模块：Authentication / 身份认证
- 难度：Apprentice
- 漏洞类型：用户名枚举
- 关键词：登录错误提示、响应差异、Burp Intruder、爆破

---

## 2. 漏洞背景

用户名枚举是指应用在认证过程中泄露了某个用户名是否存在。

在这个 lab 中，登录功能对“用户名不存在”和“密码错误”返回了不同的错误提示。攻击者可以先识别有效用户名，再针对有效用户名进行更精准的密码爆破。

---

## 3. 测试思路

先使用不同的用户名和密码发送登录请求。

重点观察应用是否根据用户名返回不同响应：

- 错误提示是否不同
- 状态码是否不同
- 响应长度是否不同
- 响应时间是否不同

如果有效用户名和无效用户名产生的响应存在差异，就可能存在用户名枚举漏洞。

---

## 4. 关键请求

```http
POST /login HTTP/2
Host: vulnerable-site.web-security-academy.net
Cookie: session=[REDACTED]
Content-Type: application/x-www-form-urlencoded

username=test&password=123456
```

---

## 5. 利用过程

1. 使用 Burp Suite 抓取登录请求。
2. 将请求发送到 Intruder。
3. 将 `username` 参数设置为 payload 位置。
4. 导入用户名列表。
5. 启动攻击并比较响应差异。
6. 找到产生不同错误提示的有效用户名。
7. 使用该有效用户名继续测试密码。
8. 使用发现的账号密码登录并完成 lab。

---

## 6. 漏洞根因

应用对不同认证失败场景返回了不同错误提示。

例如：

- 用户名不存在
- 密码错误

这种差异会泄露用户名是否存在。

---

## 7. 修复建议

- 登录失败时统一返回通用提示，例如 `Invalid username or password`。
- 尽量保持失败响应的状态码、长度和时间一致。
- 对登录尝试加入频率限制。
- 加入异常登录检测和账号保护机制。
- 不要暴露用户名或邮箱是否已注册。

---

## 8. 总结

这个 lab 的核心收获是：

> 认证失败提示不应该泄露用户名是否存在。
