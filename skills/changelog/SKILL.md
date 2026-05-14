---
name: changelog
description: 用于记录项目开发和发布过程中的有意义变更，并维护 changelog、版本记录和发布说明。
---

# Changelog

## Rule

- 除固定关键词外，使用中文。
- 路径使用 `docs/releases/unreleased.md`。
- 完成一个用户或工程上有意义的变更单元时更新。
- 发布 tag 时归档：将 `docs/releases/unreleased.md` 保存为 `docs/releases/<version>.md`，标题改为 `# <version> - <YYYY-MM-DD>`，然后重置新的 `unreleased.md`。

## Template

```markdown
# Unreleased

## Added

<!-- 新添加的功能。 -->

-

## Changed

<!-- 对现有功能的变更。 -->

-

## Deprecated

<!-- 已经不建议使用、未来会移除的功能。 -->

-

## Removed

<!-- 已经移除的功能。 -->

-

## Fixed

<!-- 对 bug 的修复。 -->

-

## Security

<!-- 对安全性的改进。 -->

-
```
