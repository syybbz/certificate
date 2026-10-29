# Domain Docs

本文说明 engineering skills 在探索代码库时应如何使用本仓库的领域文档。

## 探索前阅读

- 根目录的 **`GLOSSARY.md`**
- 如果根目录存在 **`GLOSSARY-MAP.md`**，它会指向各 context 的 `GLOSSARY.md`；读取与当前主题相关的文件
- **`docs/adr/`** 中与即将修改区域相关的 ADR
- 在 multi-context 仓库中，还应检查 `src/<context>/docs/adr/` 中的 context-specific 决策

如果这些文件不存在，**直接继续，不作提示**。不要报告文件缺失，也不要预先建议创建。`/domain-modeling` skill（可通过 `/grill-with-docs` 和 `/improve-codebase-architecture` 使用）会在术语或决策真正明确后按需创建这些文件。

## 文件结构

本仓库采用 single-context 布局：

```text
/
├── GLOSSARY.md
├── docs/adr/
│   ├── 0001-event-sourced-orders.md
│   └── 0002-postgres-for-write-model.md
└── src/
```

供其他仓库参考，存在根目录 `GLOSSARY-MAP.md` 时表示使用 multi-context 布局：

```text
/
├── GLOSSARY-MAP.md
├── docs/adr/                          ← 系统级决策
└── src/
    ├── ordering/
    │   ├── GLOSSARY.md
    │   └── docs/adr/                  ← context-specific 决策
    └── billing/
        ├── GLOSSARY.md
        └── docs/adr/
```

## 使用 glossary 中的词汇

当输出内容需要命名领域概念时，例如 issue 标题、重构提议、假设或测试名称，应使用 `GLOSSARY.md` 定义的术语。不要改用 glossary 明确避免的同义词。

如果 glossary 尚未包含所需概念，这可能意味着正在创造项目并未使用的新语言，应重新考虑；也可能表示确实存在缺口，应记录下来交由 `/domain-modeling` 处理。

## 标明与 ADR 的冲突

如果输出与已有 ADR 冲突，应明确指出，而不是静默覆盖：

> _这与 ADR-0007（event-sourced orders）冲突，但值得重新讨论，因为……_
