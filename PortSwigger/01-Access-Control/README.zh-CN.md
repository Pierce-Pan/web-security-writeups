# Access Control Labs / 访问控制漏洞

**中文** | [English](./README.md)

访问控制漏洞通常发生在：用户可以访问或操作超出自身权限范围的资源或功能。

本目录重点记录以下类型：

- 垂直越权
- 水平越权
- IDOR / 不安全的直接对象引用
- 基于 Header 的访问控制绕过
- 基于 HTTP Method 的访问控制绕过
- 多步骤业务流程中的权限校验缺失

---

## 推荐重点 Lab

| 优先级 | Lab | 漏洞类型 | 为什么值得写 |
|---|---|---|---|
| P0 | Insecure direct object references | IDOR | 真实业务中非常常见 |
| P0 | User ID controlled by request parameter | 水平越权 | 经典对象级权限校验失败 |
| P0 | User ID controlled by request parameter with password disclosure | IDOR + 敏感信息泄露 | 危害直观，适合求职展示 |
| P0 | User ID controlled by request parameter with data leakage in redirect | 重定向过程信息泄露 | 体现你会检查完整响应 |
| P0 | User role controlled by request parameter | 垂直越权 | 权限参数由客户端控制 |
| P0 | User role can be modified in user profile | 访问控制缺陷 | 后端接收隐藏敏感字段 |
| P0 | URL-based access control can be circumvented | Header 绕过 | 反向代理或路由差异导致绕过 |
| P0 | Method-based access control can be circumvented | HTTP Method 绕过 | 常见配置错误 |
| P0 | Multi-step process with no access control on one step | 业务逻辑访问控制缺陷 | 非常接近真实业务场景 |
| P0 | Referer-based access control | Header 鉴权缺陷 | Referer 可以被用户伪造 |

---

## 推荐写作顺序

1. IDOR 静态文件 / transcript
2. User ID controlled by request parameter
3. User ID with password disclosure
4. User ID data leakage in redirect
5. User role controlled by request parameter
6. User role modified in profile
7. URL-based access control bypass
8. Method-based access control bypass
9. Multi-step process missing access control
10. Referer-based access control
