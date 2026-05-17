---
name: changelog
description: 用于记录项目开发和发布过程中的有意义变更，并维护 changelog、版本记录和发布说明。
---

# Changelog

## Rule

- 除固定关键词外，使用中文。
- 默认维护仓库根目录 `CHANGELOG.md`。
- 有意义的用户或工程变更，写入对应 `CHANGELOG.md` 的 `[Unreleased]` 区块；没有该区块时先创建。
- 发布 tag 时，将当前 `[Unreleased]` 标题改为 `[<version>] - <YYYY-MM-DD>`。
- **重点：`[Unreleased]` 中尚未发布的条目发生后续调整时，只修改原条目，让它描述最终状态，不要新增一条记录来描述这次调整。**
  例如：本周期在 `Added` 中记录了一个新功能，随后修复这个新功能本身的问题时，应直接更新该 `Added` 条目，使其描述修复后的最终功能，不要再新增 `Fixed`。同一原则适用于 `Changed`、`Deprecated`、`Removed`、`Security` 等所有 `[Unreleased]` 分类：如果调整对象仍是本周期尚未发布的条目，应更新原条目；只有修复已发布版本中已经存在的问题时，才新增 `Fixed`。

## Template

```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

<!-- 新添加的功能。 -->

-

### Changed

<!-- 对现有功能的变更。 -->

-

### Deprecated

<!-- 已经不建议使用、未来会移除的功能。 -->

-

### Removed

<!-- 已经移除的功能。 -->

-

### Fixed

<!-- 对 bug 的修复。 -->

-

### Security

<!-- 对安全性的改进。 -->

-

## [<version>] - <YYYY-MM-DD>

...
```
