# 贡献指南

PM Skills Marketplace 由 [Paweł Huryn](https://www.productcompass.pm) (pawel@productcompass.pm) 维护。欢迎各种贡献——无论是 bug 修复、笔误更正，还是新技能创意。

## 如何贡献

- **Bug 和小修复** — 直接提交 PR。
- **新技能、命令或较大改动** — 先开 issue 讨论方案。

## 准则

- PR 聚焦 — 一个 PR 只做一件事。
- 遵循现有模式：技能是名词（领域知识），命令是动词（工作流）。
- 每个技能必须有包含 `name` 和 `description` 的 frontmatter。每个命令必须有 `description` 和 `argument-hint`。
- 技能的 `name` 必须与其目录名一致。
- 命令中不要跨插件引用。后续步骤建议只用自然语言表述。
- 所有贡献者都会被公开列出。
- 提交前请运行验证器：`python3 validate_plugins.py`

## 许可证

参与贡献即表示你同意你的贡献将在 [MIT 许可证](LICENSE) 下发布。
