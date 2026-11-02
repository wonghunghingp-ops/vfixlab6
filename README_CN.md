# FixLab — 已验证漏洞研究

[English](README.md) | [FixLab 官网](https://vfixlab.com)

FixLab（飞克实验室）发布的漏洞研究，都先在自有隔离靶场里复现过，每套修复方案都端到端跑通过才推荐。跑不通的修复，我们会明说跑不通，不会硬 claim。

这个库是 FixLab 已验证漏洞写法的总索引。每个漏洞都有独立的库，里面是一整套：概述、受影响与修复版本、技术分析、FixLab 验证证据（含诚实边界）、检测方法、修复处置、参考。

## 已验证写法

| 漏洞 | CVE | 严重度 | 修复版本 | 写法 |
|---|---|---|---|---|
| PHP2Shell — PHP 引擎堆 UAF 远程代码执行 | CVE-2026-109618、CVE-2026-109619 | CVSS 9.2 | PHP 8.4.27 | [php2shell-cve-2026-109618](https://github.com/wonghunghingp-ops/php2shell-cve-2026-109618) |
| Node2Shell — Node.js Brotli 解码器越界写远程代码执行 | CVE-2026-111497 | CVSS 9.2 | Node 24.22.1 / 22.23.4 / 26.12.1 | [node2shell-cve-2026-111497](https://github.com/wonghunghingp-ops/node2shell-cve-2026-111497) |
| LiteLLM 1.107.0 供应链投毒 — 投毒 Wheel、凭证窃取、持久化 .pth 后门 | —（CWE-506） | 严重 | litellm==1.106.2 + 手动清理 + 全部凭证轮换 | [litellm-1-107-0-supply-chain-compromise](https://github.com/wonghunghingp-ops/litellm-1-107-0-supply-chain-compromise) |
| Cursor 市场木马化 Claude Code 扩展 — 经 svc-telemetry 密钥的 SSH 后门 | — | 严重 | 扩展 2.1.314 + 删密钥与持久化 + 轮换 | [cursor-claude-code-trojanized-extension](https://github.com/wonghunghingp-ops/cursor-claude-code-trojanized-extension) |
| GitLab Onigmo RCE — Ruby 正则整数溢出 | CVE-2026-97229、CVE-2026-110264 | CVSS 10.0 | GitLab 19.2.8 / 19.3.5 / 19.4.2 及后续补丁版 + Ruby 3.3.13 | [gitlab-onigmo-cve-2026-97229](https://github.com/wonghunghingp-ops/gitlab-onigmo-cve-2026-97229) |

## FixLab 验证什么

- **复现：** 漏洞在自有服务器的隔离实验里触发，只绑回环地址，用 dummy 数据。不碰任何第三方系统。
- **修复：** 同一套验证打修复版，确认链条被挡住。
- **诚实边界：** 完整复现做不到的地方（例如完整 GitLab 实例超出实验内存），我们在组件层验证，并明说哪些跑了、哪些没跑。
- **不发武器：** 写法讲机制、验证结果、检测和修复，不贴完整 exploit 脚本和触发体。

## FixLab 服务

FixLab 提供漏洞修复服务：单次修复、AI 工具链安全检查与审计、全面审计、月度订阅。详情与定价见官网。

- 官网：https://vfixlab.com

## 分享

本站内容可署名 FixLab 并附 https://vfixlab.com 链接后分享。
