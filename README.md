# FixLab — Verified Vulnerability Research

[中文版](README_CN.md) | [FixLab 官网](https://vfixlab.com)

FixLab (飞克实验室) publishes vulnerability research that is reproduced in our own isolated lab before it is written up, and every fix is run through end to end before we recommend it. If a fix cannot be verified, we say so instead of claiming it.

This repository is the index of FixLab's verified vulnerability writeups. Each vulnerability has its own dedicated repository with a full writeup: overview, affected and fixed versions, technical analysis, FixLab verification evidence (including honest boundaries), detection steps, remediation, and references.

## Verified writeups

| Vulnerability | CVE | Severity | Fixed version | Writeup |
|---|---|---|---|---|
| PHP2Shell — PHP engine heap use-after-free RCE | CVE-2026-109618, CVE-2026-109619 | CVSS 9.2 | PHP 8.4.27 | [php2shell-cve-2026-109618](https://github.com/wonghunghingp-ops/vfixlab1) |
| Node2Shell — Node.js Brotli decoder out-of-bounds write RCE | CVE-2026-111497 | CVSS 9.2 | Node 24.22.1 / 22.23.4 / 26.12.1 | [node2shell-cve-2026-111497](https://github.com/wonghunghingp-ops/vfixlab2) |
| LiteLLM 1.107.0 supply-chain compromise — poisoned wheels, credential theft, persistent .pth backdoor | — (CWE-506) | Critical | litellm==1.106.2 + manual cleanup + credential rotation | [litellm-1-107-0-supply-chain-compromise](https://github.com/wonghunghingp-ops/vfixlab3) |
| Trojanized Claude Code extension on Cursor Marketplace — SSH backdoor via svc-telemetry key | — | Critical | Extension 2.1.314 + key/persistence removal + rotation | [cursor-claude-code-trojanized-extension](https://github.com/wonghunghingp-ops/vfixlab4) |
| GitLab Onigmo RCE — Ruby regex integer overflow | CVE-2026-97229, CVE-2026-110264 | CVSS 10.0 | GitLab 19.2.8 / 19.3.5 / 19.4.2 and later patch releases + Ruby 3.3.13 | [gitlab-onigmo-cve-2026-97229](https://github.com/wonghunghingp-ops/vfixlab5) |

## What FixLab verifies

- **Reproduction:** the vulnerability is triggered in an isolated lab on our own servers, loopback only, with dummy data. No third-party system is touched.
- **Fix:** the patched version is run against the same proof to confirm the chain is blocked.
- **Honest boundaries:** where a full reproduction is not possible (for example, a complete GitLab instance exceeding our lab's memory), we verify at the component level and state plainly what was and was not run.
- **No turnkey weapons:** writeups describe mechanisms, verification outcomes, detection, and fixes. They do not publish full exploit scripts or trigger payloads.

## FixLab services

FixLab provides vulnerability remediation services: single fixes, AI toolchain security reviews and audits, full audits, and monthly subscriptions. Details and pricing are on the website.

- Website: https://vfixlab.com

## License and reuse

Content here may be shared with attribution to FixLab and a link to https://vfixlab.com.
