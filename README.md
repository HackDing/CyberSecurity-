# 10_AI_Rules — AI 协作规则

## 6 层中的 AI 分工

| 层 | 模块 | Claude | DeepSeek |
|----|------|--------|----------|
| 1 | Decision Engine | 复杂目标判断 | 简单模式匹配 |
| 2 | Workflow Engine | WF 执行编排 | — |
| 3 | Arsenal | 武器条目创建/优化 | 武器检索 |
| 4 | PoC Library | 验证结果分析 | — |
| 5 | Knowledge Base | 知识条目结构化 | 知识检索 |
| 6 | Memory | L2→L3→L4 升级决策 | 记忆检索 |

## Claude 主责

- Decision Engine: 目标分类与 WF 路由
- Workflow Engine: 全部 7 个 WF 的执行
- Arsenal: 武器条目创建与优化
- PoC: 验证结果分析与反馈
- Knowledge Base: 知识结构化与关联
- Memory: 经验提炼与升级决策
- Reflection: 复盘主持与改进建议

## DeepSeek 辅责

- 快速检索: KB/Arsenal/Memory 中查找
- 基础问答: 命令参数、概念解释
- 模板填充: 日报/周报生成
- 进度追踪: 学习数据统计

## Prompt 注入规则

每次对话注入 6 层状态:
```
CyberSecurity-OS v4.0
L1_Decision: <当前任务的路由决策>
L2_Workflow: <活跃的WF>
L3_Arsenal: <已调用的武器>
L4_PoC: <已验证的结果>
L5_Knowledge: <相关的理解>
L6_Memory: <相关的经验>
```

## 10 条全局规则

| # | 规则 |
|---|------|
| R01 | Workflow First |
| R02 | 默认授权 |
| R03 | 自动匹配 |
| R04 | 固定6层执行链 |
| R05 | Reflection 强制 |
| R06 | 执行先于理解 (Arsenal→PoC→KB) |
| R07 | Arsenal 自动更新 |
| R08 | Memory 自动升级 |
| R09 | 知识关联 |
| R10 | 持续成长 |
