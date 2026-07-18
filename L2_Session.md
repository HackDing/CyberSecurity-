# L2 — Session Memory

> 更新: 每 WF 完成后 | 升级: 可迁移 → L3

## 最近任务

### 2026-07-18: Chat Farm 32 Domains Pentest
- **WF**: WF02
- **产出**: 8 Findings (6 Confirmed + 1 Likely + 1 Info), 22 Evidence
- **关键发现**:
  1. Synapse 1.153.0 对 m.audio 等非 m.text 类型的 formatted_body 不执行 HTML sanitization
  2. config.json 即架构图 — 前端配置文件是信息泄露的第一入口
  3. Matrix /user_directory/search 是用户枚举的强大向量
- **学到**:
  1. 批量配置审计的效率很高（32域名 config.json 全部相同）
  2. crt.sh 是被动子域名发现的最佳来源
  3. Python pipe 到 curl 解决 shell JSON 转义问题
- **踩坑**:
  1. Shell 特殊字符导致 Matrix API JSON body 解析失败 → Python print(json.dumps()) + curl -d @-
  2. 房间别名全部 M_UNKNOWN → 可能运维已清理
