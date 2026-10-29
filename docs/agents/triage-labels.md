# Triage Labels

Skills 使用五个标准 triage 角色。下表将这些角色映射到本仓库 issue tracker 实际使用的状态字符串。

| mattpocock/skills 中的标签 | 本仓库 tracker 中的标签 | 含义 |
| --- | --- | --- |
| `needs-triage` | `needs-triage` | 需要维护者评估此 issue |
| `needs-info` | `needs-info` | 等待报告者提供更多信息 |
| `ready-for-agent` | `ready-for-agent` | 已完整定义，可交给 AFK agent |
| `ready-for-human` | `ready-for-human` | 需要由人类实现 |
| `wontfix` | `wontfix` | 不会处理 |

当 skill 提到某个角色时，例如“应用 AFK-ready triage 标签”，使用本表中对应的标签字符串。

对于本地 Markdown tracker，将该字符串记录在 issue 文件顶部附近的 `Status:` 行中。
