# WF01 — Learning Workflow

## 路由条件
输入包含学习意图关键词 → Decision Engine 路由到此 WF

## 执行链

```
Goal         → 明确学习主题 + 设定深度
Information  → 收集学习资源 (官方文档/教程/案例)
Analysis     → 理解概念 + 原理 + 机制
Verification → 实验验证 (调用 03_Arsenal, 记录到 04_PoC_Library)
Result       → 学习笔记 + 实验记录 + 知识卡片
Report       → 学习报告 → 08_Reports/Learning/
    │
    ▼
Reflection   → 理解程度自评 / 最大认知突破 / 仍然模糊的地方
    │
    ├──→ 03_Arsenal: 实验中的有效命令/脚本
    ├──→ 04_PoC_Library: 验证过程和结果
    ├──→ 05_Knowledge_Base: 满足5条件则写入知识条目
    └──→ 06_Memory: L2→L3 (掌握≥7/10)
```

## 学习深度控制

| 深度 | 目标 | 验证要求 |
|------|------|----------|
| 入门 | 能解释概念 + 能使用工具 | 完成基础实验 |
| 进阶 | 理解原理 + 能绕过基础防护 | 完成进阶实验 |
| 实战 | 能在真实/模拟场景中利用 | 完成靶场/授权测试 |
