# WF07 — Writeup Workflow

## 路由条件
Writeup/复盘/总结意图 → Decision Engine 路由到此 WF

## 执行链

```
Goal         → 确认Writeup主题 + 来源(WF06/CTF/漏洞研究)
Information  → 收集原始材料: 笔记/截图/命令/Payload
Analysis     → 重组攻击过程 + 提取关键思路 + 抽象通用模式
Verification → 确认步骤可复现 (必要时重新验证)
Result       → 完整Writeup: 背景→思路→过程→分析→总结
Report       → Writeup → 08_Reports/CTF/ 或对应分类
    │
    ▼
Reflection   → 这个Writeup能让别人复现吗?
    │
    ├──→ 03_Arsenal: 提取有效Payload/命令/脚本
    ├──→ 04_PoC_Library: 归档完整验证过程
    ├──→ 05_Knowledge_Base: 漏洞分析通用化 + 攻击模式抽象
    └──→ 06_Memory: L3核心经验 → L4独特方法论/创新技术
```

## Writeup 标准

```
背景 → 思路(最重要的部分) → 过程(Step by Step) → 分析 → 总结 → 经验
```

**思路部分是核心**——不仅是"做了什么"，更是"为什么这样做"。
