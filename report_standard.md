# Report Standard — 全局报告标准

> 所有 WF 产出的报告必须遵循此标准
> 基于 CHAT_FARM_32_DOMAINS_PENTEST_REPORT 提炼

## 报告结构 (9 章节固定)

```
1. 目标 (Goal)             — 授权范围 + 测试目标
2. Finding 概览            — 汇总表
3. Confirmed Finding       — 已确认漏洞详情
4. Likely Finding          — 高可能性漏洞
5. Possible / Unknown      — 待确认发现
6. 目标达成情况            — 目标 vs 实际
7. 建议 (Recommendations)  — 按优先级
8. 技术架构总结            — 架构图 + 资产分类
9. 附录                    — 工具/API/资产/Evidence索引
```

## Finding 分类体系

### Confidence 四级

| 级别 | 含义 | 要求 |
|------|------|------|
| **Confirmed** | 已确认利用成功 | 有完整 PoC + Evidence |
| **Likely** | 有强证据，未完全验证 | 有部分 Evidence |
| **Possible** | 有线索，待深入 | 至少 1 条线索 |
| **Info** | 信息性发现 | 无风险但有价值 |

### Finding ID 规范

```
F-001, F-002, F-003...  全局递增，不重复
```

### Evidence ID 规范

```
EV-001, EV-002, EV-003...  全局递增
每个 Evidence 关联到 Finding
```

## Finding 条目标准结构 (每个 Confirmed Finding)

```markdown
### [F-XXX] <名称> — <严重度>

| 字段表 | (ID/Category/Confidence/State/Evidence/CWE/OWASP) |

#### 摘要        — 一段话
#### 影响范围    — 列表
#### 复现步骤    — 编号步骤 + 代码块
#### 关键证据    — 代码块
#### 漏洞验证过程 — Detection → Verification → Confirmation
#### 影响分析    — 即时/横向/链式/持久化
#### 风险评级    — 5维度表格 (可利用性/影响范围/数据敏感度/修复难度/综合)
#### 修复建议    — 立即/短期/中期 分级
```

## 风险评级矩阵

| 维度 | 说明 |
|------|------|
| 可利用性 | 攻击难度: 极高(无需认证)/高(低权限)/中(特定条件)/低(理论) |
| 影响范围 | 全网/多系统/单系统 |
| 数据敏感度 | 高(PII/凭证)/中(内部信息)/低(公开信息) |
| 修复难度 | 低(配置修改)/中(代码修改)/高(架构变更) |

## 修复优先级

| 优先级 | 触发条件 |
|--------|----------|
| **立即** | CRITICAL + HIGH 风险 |
| **短期** | Likely Finding + MEDIUM 风险 |
| **中期** | Possible Finding + LOW 风险 |

## 附录标准

每个报告必须包含:
1. 工具与命令清单
2. 关键 API 端点表
3. 发现资产清单
4. Evidence 索引表 (ID/Type/Source/Description)
