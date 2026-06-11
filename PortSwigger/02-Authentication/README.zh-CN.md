# Authentication Labs / 身份认证漏洞

**中文** | [English](./README.md)

身份认证漏洞通常发生在：应用没有正确验证用户身份，或者登录、MFA、Remember-me、密码重置等认证流程存在逻辑缺陷。

本目录重点记录以下类型：

- 用户名枚举
- 爆破防护绕过
- MFA / 2FA 逻辑缺陷
- Remember-me Cookie 弱设计
- 密码重置漏洞
- 密码修改流程缺陷

---

## 推荐重点 Lab

| 优先级 | Lab | 漏洞类型 | 为什么值得写 |
|---|---|---|---|
| P0 | Username enumeration via different responses | 用户名枚举 | 基础但非常高频 |
| P0 | Username enumeration via subtly different responses | 用户名枚举 | 体现细节观察能力 |
| P0 | Username enumeration via response timing | 时间侧信道 | 技术含量更高 |
| P0 | Broken brute-force protection, IP block | 爆破防护绕过 | 常见弱防护设计 |
| P0 | Username enumeration via account lock | 账户锁定侧信道 | 防护机制反向泄露信息 |
| P0 | 2FA simple bypass | MFA 绕过 | 直接绕过认证流程 |
| P0 | 2FA broken logic | MFA 逻辑缺陷 | Token 未正确绑定用户或会话 |
| P0 | Brute-forcing a stay-logged-in cookie | 弱 Remember-me Token | Cookie 设计与哈希破解 |
| P0 | Offline password cracking | Cookie 泄露 + 离线破解 | 很好的组合漏洞案例 |
| P0 | Password reset broken logic | 密码重置缺陷 | 真实业务中危害很高 |
| P0 | Basic password reset poisoning | Host Header 攻击 | 很适合求职展示 |
| P0 | Password reset poisoning via middleware | Header 型重置链接污染 | Host / X-Forwarded-Host 进阶案例 |
| P0 | Password brute-force via password change | 密码修改逻辑缺陷 | 认证流程与业务逻辑结合 |
