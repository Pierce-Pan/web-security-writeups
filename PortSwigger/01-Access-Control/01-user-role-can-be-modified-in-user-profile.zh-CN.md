# Lab: User role can be modified in user profile

**中文** | [English](./01-user-role-can-be-modified-in-user-profile.en.md)

## 1. Lab 基本信息

- 平台：PortSwigger Web Security Academy
- 模块：Access Control / 访问控制
- 难度：Apprentice
- 漏洞类型：垂直越权 / 访问控制缺陷
- 关键词：roleid、JSON 参数篡改、隐藏字段、权限提升

---

## 2. 漏洞背景

这个 lab 展示的是用户资料修改功能中的访问控制缺陷。

应用允许普通用户在个人资料修改请求中提交类似 `roleid` 的敏感权限字段。如果后端直接信任这个由客户端提交的字段，攻击者就可以把自己的权限从普通用户提升为管理员。

这类问题在真实业务中很常见，尤其是开发者只在前端隐藏敏感字段，但后端没有做严格字段校验的情况下。

---

## 3. 测试思路

使用普通用户登录后，观察修改邮箱或修改个人资料功能产生的请求。

重点检查：

- 响应中是否出现 `roleid`、`isAdmin`、`permission` 等字段？
- 是否可以在 JSON 请求体中手动添加这些字段？
- 后端是否会接受并应用修改后的角色值？
- 修改后是否可以访问管理员功能？

---

## 4. 关键请求

```http
POST /my-account/change-email HTTP/2
Host: vulnerable-site.web-security-academy.net
Cookie: session=[REDACTED]
Content-Type: application/json

{
  "email": "test@example.com",
  "roleid": 2
}
```

---

## 5. 利用过程

1. 使用普通用户登录。
2. 修改邮箱，并在 Burp Suite 中抓取对应请求。
3. 将请求发送到 Repeater。
4. 在 JSON 请求体中添加 `roleid` 字段。
5. 发送修改后的请求。
6. 访问管理员后台。
7. 使用获得的管理员权限完成 lab 目标。

---

## 6. 漏洞根因

后端信任了用户可控的权限字段。

`roleid`、`isAdmin`、`permission` 这类权限相关字段不应该由普通用户提交，也不应该被个人资料修改接口直接接收。

---

## 7. 修复建议

- 普通用户请求中不应接收任何权限相关字段。
- 对用户可修改字段使用服务端白名单。
- 修改用户角色必须通过独立的管理员接口完成。
- 所有权限判断必须在服务端完成。
- 角色变更应记录审计日志。

---

## 8. 总结

这个 lab 的核心收获是：

> 隐藏字段不是安全机制。任何来自客户端的敏感字段都必须默认不可信。
