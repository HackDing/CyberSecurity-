# WF05 — Threat Analysis Workflow

## 路由条件
CVE编号 / 漏洞名 / 攻击技术名 → Decision Engine 路由到此 WF

## 执行链

```
Goal         → 确认CVE编号 + 影响范围
Information  → NVD详情 + CVSS + 公开PoC + 补丁状态 + 野外利用
Analysis     → 漏洞类型 + 根因 + 触发条件 + 攻击向量
Verification → 搭建实验环境复现漏洞
               调用 03_Arsenal 相关 Payload
               验证结果记录到 04_PoC_Library/Exploitation/
Result       → 技术分析 + PoC + 检测方法 + 缓解措施
Report       → 威胁分析报告 → 08_Reports/Threat/
    │
    ▼
Reflection   → 这个漏洞根本的设计缺陷是什么?
    │
    ├──→ 03_Arsenal: PoC代码 + 检测规则(Sigma/YARA) + Docker实验环境
    ├──→ 04_PoC_Library: 完整复现过程的PoC
    ├──→ 05_Knowledge_Base: 漏洞类型的通用原理+检测+防御模式
    └──→ 06_Memory: L3漏洞研究SOP → L4基础性漏洞核心原理
```

## 分析维度

| 维度 | 内容 |
|------|------|
| 基本信息 | CVE, CVSS, 类型, 产品, 版本 |
| 原理 | 漏洞类型, 根因, 触发条件 |
| 利用 | 攻击前提, 攻击向量, 利用复杂度 |
| 检测 | 日志特征, 流量特征, 主机特征, Sigma/YARA规则 |
| 防御 | 官方补丁, 临时缓解, WAF规则, 配置加固 |
