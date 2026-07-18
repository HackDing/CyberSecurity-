# 00_Dashboard — 系统仪表盘

> 更新: 2026-07-18

## 报告标准

所有报告遵循统一结构:
- **Finding ID**: F-001, F-002... 全局唯一
- **Evidence ID**: EV-001, EV-002... 与 Finding 关联
- **Confidence**: Confirmed / Likely / Possible / Info
- **Finding 详情**: 字段表 → 摘要 → 影响 → 复现 → 证据 → 验证 → 风险矩阵 → 修复
- **完整报告**: 9 章节固定结构 (见 09_Templates/pentest_report.md)

## 6 层状态

| 层 | 模块 | 状态 |
|----|------|------|
| 1 | Decision Engine | ✅ |
| 2 | Workflow Engine | ✅ |
| 3 | Arsenal | ✅ 4种子 |
| 4 | PoC Library | ✅ 1种子 |
| 5 | Knowledge Base | ✅ 1种子 |
| 6 | Memory | ✅ L1-L4初始化 |

## 快捷入口

```
输入域名     → 01→02(WF03)→...→06
输入 URL     → 01→02(WF02)→...→06
输入 CVE     → 01→02(WF05)→...→06
输入 "学 X"  → 01→02(WF01)→...→06
```
