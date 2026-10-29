# Issue tracker：本地 Markdown

本仓库的 issue 和 spec 以 Markdown 文件形式存放在 `.scratch/` 中。

## 约定

- 每个 feature 使用一个目录：`.scratch/<feature-slug>/`
- Spec 文件为 `.scratch/<feature-slug>/spec.md`
- 每个 implementation issue 使用一个独立文件，存放于 `.scratch/<feature-slug>/issues/<NN>-<slug>.md`
- Issue 从 `01` 开始编号，不使用单个合并的 tickets 文件
- Triage 状态记录在每个 issue 文件顶部附近的 `Status:` 行中，角色字符串见 `triage-labels.md`
- 评论和对话历史追加到文件底部的 `## Comments` 标题下

## 当 skill 要求“publish to the issue tracker”时

在 `.scratch/<feature-slug>/` 下创建新文件；目录不存在时一并创建。

## 当 skill 要求“fetch the relevant ticket”时

读取引用路径下的文件。用户通常会直接提供文件路径或 issue 编号。

## Wayfinding 操作

供 `/wayfinder` 使用。一个 **map** 文件对应每个 ticket 的一个 **child** 文件。

- **Map**：`.scratch/<effort>/map.md`，包含 Notes、Decisions-so-far 和 Fog 正文
- **Child ticket**：`.scratch/<effort>/issues/NN-<slug>.md`，从 `01` 开始编号，正文中记录问题；`Type:` 行记录 ticket 类型（`research`、`prototype`、`grilling` 或 `task`），`Status:` 行记录 `claimed` 或 `resolved`
- **Blocking**：在文件顶部附近使用 `Blocked by: NN, NN` 行；仅当其中列出的所有文件都处于 `resolved` 状态时，该 ticket 才解除阻塞
- **Frontier**：扫描 `.scratch/<effort>/issues/`，寻找开放、未阻塞且未被认领的文件；编号最小者优先
- **Claim**：开始工作前，将 `Status:` 设置为 `claimed` 并保存
- **Resolve**：在 `## Answer` 标题下追加答案，将 `Status:` 设置为 `resolved`，然后在 `map.md` 的 Decisions-so-far 中追加上下文指针（摘要和链接）
