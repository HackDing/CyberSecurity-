# WF06 — Lab Workflow

## 路由条件
HTB / THM / DVWA / VulnHub / 靶场标识 → Decision Engine 路由到此 WF

## 执行链

```
Goal         → 确认平台 + 目标 + 难度
Information  → 端口扫描 + 服务识别 + Web枚举 + 漏洞扫描
Analysis     → 攻击路径分析 + 入口点选择
Verification → 逐步攻击: 入口→提权→横向→目标
               调用 03_Arsenal 对应域的武器
               每步结果记录到 04_PoC_Library
Result       → Flag/证明 + 完整攻击过程 + 经验总结
Report       → Lab记录 → 08_Reports/Lab/ + → WF07 Writeup
    │
    ▼
Reflection   → 卡在哪里最久? / 独立完成了多少?
    │
    ├──→ 03_Arsenal: 有效Payload + 提权脚本 + 扫描命令组合
    ├──→ 04_PoC_Library: 完整攻击链的PoC
    ├──→ 05_Knowledge_Base: 新学攻击技术原理 + 特定服务攻击面
    └──→ 06_Memory: L2实验记录 → L3成功技术路径 → L4独特技巧
```

## 攻击阶段

```
信息收集 → 入口发现 → 初始立足点 → 权限提升 → 横向移动 → 目标达成
```

每阶段记录: 发现 | 利用方式 | 命令 | 结果 | 截图
