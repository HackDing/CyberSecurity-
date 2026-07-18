# WF04 — Log Analysis Workflow

## 路由条件
日志文件输入 → Decision Engine 路由到此 WF

## 执行链

```
Goal         → 确认日志类型 + 时间范围
Information  → 解析日志格式 + 提取字段(时间/IP/UA/状态码/请求)
Analysis     → 事件关联 + 异常检测 + 攻击特征识别 + 时间线重建
Verification → 确认异常是否为真实攻击 (误报排除)
               调用 03_Arsenal/Detection/* 的检测规则
               验证结果记录到 04_PoC_Library
Result       → 攻击链还原 + IOC清单 + MITRE映射
Report       → 日志分析报告 → 08_Reports/Log/
    │
    ▼
Reflection   → 日志源是否完整? / 分析有遗漏吗?
    │
    ├──→ 03_Arsenal: 分析命令 + Sigma/YARA检测规则
    ├──→ 04_PoC_Library: 确认的攻击事件
    ├──→ 05_Knowledge_Base: 攻击模式特征总结 + 日志字段价值评估
    └──→ 06_Memory: L3 新攻击模式 → L4 成熟日志分析SOP
```

## 分析维度

| 维度 | 检测内容 |
|------|----------|
| 高频访问 | 扫描/DDoS 特征 |
| SQL注入 | `'`, `union`, `select`, `sleep` |
| XSS | `<script>`, `javascript:`, `onerror` |
| 路径遍历 | `../`, `..\` |
| 命令注入 | `|`, `;`, `$()`, `` `` |
| 异常UA | 非浏览器 User-Agent |
| 地理异常 | 不可能的地理跳转 |
| 错误码 | 大量403/500 |
