# Target Classifier — 目标分类器

## 分类决策树

```
INPUT
│
├── 匹配域名正则?
│   ├── YES → 是已知靶场域名?
│   │   ├── YES → WF06 Lab
│   │   └── NO  → WF03 Domain Analysis
│   └── NO → 继续
│
├── 匹配 URL 正则?
│   ├── YES → WF02 Web Pentest (若靶场/授权)
│   └── NO → 继续
│
├── 匹配 IP 正则?
│   ├── YES → 是靶场 IP?
│   │   ├── YES → WF06 Lab
│   │   └── NO  → WF03 Domain Analysis (被动)
│   └── NO → 继续
│
├── 匹配 CVE 正则?
│   ├── YES → WF05 Threat Analysis
│   └── NO → 继续
│
├── 是日志文件?
│   ├── YES → WF04 Log Analysis
│   └── NO → 继续
│
├── 包含学习意图关键词?
│   ├── YES → WF01 Learning
│   └── NO → 继续
│
├── 包含 Writeup 意图关键词?
│   ├── YES → WF07 Writeup
│   └── NO → 继续
│
├── 包含靶场标识关键词?
│   ├── YES → WF06 Lab
│   └── NO → 继续
│
└── 无法分类 → 请求用户澄清
```

## 正则模式

| 类型 | 正则 |
|------|------|
| 域名 | `^([a-zA-Z0-9]([a-zA-Z0-9-]*[a-zA-Z0-9])?\.)+[a-zA-Z]{2,}$` |
| IPv4 | `^(\d{1,3}\.){3}\d{1,3}$` |
| URL | `^https?://` |
| CVE | `^CVE-\d{4}-\d{4,}$` |

## 关键词映射

| 关键词 | 含义 | WF |
|--------|------|-----|
| HTB, HackTheBox, Machine | HTB 靶场 | WF06 |
| THM, TryHackMe, Room | THM 靶场 | WF06 |
| DVWA, Juice Shop, JuiceShop | Web 靶场 | WF06 |
| VulnHub, Metasploitable | 靶场 | WF06 |
| 学, 学习, 了解, 入门, 掌握, 理解, 教程 | 学习 | WF01 |
| Writeup, 复盘, 总结, 记录, 写报告 | 记录 | WF07 |
| CVE | 漏洞研究 | WF05 |
| log, 日志 | 日志分析 | WF04 |
| pcap, 流量, 抓包 | 流量分析 | WF04 |

## 已知靶场域名列表

```
hackthebox.com, hackthebox.eu
tryhackme.com
vulnhub.com
docker.local, lab.local, cyber.local
```
