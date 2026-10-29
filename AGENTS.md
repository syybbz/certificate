# 项目协作约束

## 交流语言

- **始终使用中文**与用户进行交流，包括回答、解释、代码注释和所有文字输出。
- 代码本身（变量名、函数名、字符串等）保持原样，不强制翻译。

## Agent skills

### Issue tracker

Issue 使用 `.scratch/<feature>/` 下的本地 Markdown 文件管理。详见 `docs/agents/issue-tracker.md`。

### Triage labels

使用五个默认 triage 角色，并通过 issue 文件中的 `Status:` 字段记录。详见 `docs/agents/triage-labels.md`。

### Domain docs

采用 single-context 布局：根目录使用 `GLOSSARY.md`，ADR 存放于 `docs/adr/`。详见 `docs/agents/domain.md`。
