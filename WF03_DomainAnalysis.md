# WF03 — Domain Analysis Workflow

## 路由条件
域名输入 → Decision Engine 路由到此 WF

## 执行链

```
Goal         → 确认目标域名 + 分析范围
Information  → DNS记录 + Whois + SSL证书(crt.sh) + 子域名公开情报
Analysis     → 技术栈识别 + CDN/WAF判断 + 暴露面分析 + 安全配置检查
Verification → 发现的子域名/暴露面/配置缺陷逐一确认
Result       → 风险矩阵 + 安全评分 + 防御建议
Report       → 域名安全分析报告 → 08_Reports/Domain/
    │
    ▼
Reflection   → 哪些信息源最有价值? / 分析流程能优化吗?
    │
    ├──→ 03_Arsenal: DNS/子域名一键收集脚本
    ├──→ 04_PoC_Library: 确认的配置缺陷
    ├──→ 05_Knowledge_Base: 技术栈指纹特征 + CDN识别方法
    └──→ 06_Memory: L3→L4 成熟的域名分析SOP
```

## 分析维度

| 维度 | 内容 |
|------|------|
| DNS | A/AAAA/MX/NS/TXT/CNAME/SOA, DNSSEC |
| Whois | 注册商/日期/组织 |
| SSL | 证书透明度/颁发者/有效期/SAN |
| 子域名 | crt.sh + 搜索引擎 + 公共DNS数据集 |
| 技术栈 | Web服务器/前端/后端/CDN/WAF/CMS |
| 安全配置 | HTTPS/HSTS/CSP/CORS/Cookie/DMARC |
| 暴露面 | 端口/管理入口/API/测试环境/云存储 |
