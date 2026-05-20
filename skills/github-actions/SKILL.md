---
name: github-actions
description: 创建或维护 GitHub Actions CI、tag release、Docker 打包发布 workflow 时使用。
---

# GitHub Actions

创建或维护 `.github/workflows/*.yml` 时使用。

- 除固定关键词、命令、文件名和 GitHub Actions 字段外，说明文字使用中文。
- workflow 默认使用 `actions/checkout` 并启用 Git LFS：`lfs: true`。
- PR 到 `main` 只做检查，不发布、不打包 release。
- 发布只由 `vX.Y.Z` tag 触发。
- tag 为 `vX.Y.Z` 时，项目版本号为 `X.Y.Z`；`CHANGELOG.md` 中的版本标题也写 `X.Y.Z`，不带 `v`。
- release notes 必须从 `CHANGELOG.md` 的 `## [X.Y.Z] - <YYYY-MM-DD>` 区块提取；找不到该区块时 workflow 应失败。
- 项目名、app 名和 release 资源名前缀默认使用 GitHub 仓库名。
- Rust 和 Bun 都按根目录 workspace 处理；不要探测 `backend/`。
- CI 只跑 Rust 检查，不跑前端检查。
- Docker image 信息由 Docker 模板中的 `just update-version` 输出，workflow 不自行推导镜像名。

## 选择模板

- [ci](./template/ci.yml)：所有项目共用的 PR 到 `main` 检查模板。
- [docker-release](./template/docker-release.yml)：仓库根目录存在 `docker-compose.yaml` 时使用；同时使用 [docker template](./template/docker/) 中的根 `Cargo.toml`、`package.json`、`justfile`、`docker-compose.yaml` 和 Dockerfile；Docker image tag 使用 `X.Y.Z`，release 包包含 `docker.tar`、`docker-compose.yaml`、`.env.example`、公共配置和隐私配置的 `.example` 文件，不包含 `.env`、`.env.local`、密钥、证书或私有配置。
- [tauri-release](./template/tauri-release.yml)：Tauri 项目使用。
- [app-release](./template/app-release.yml)：普通 Rust app 使用e。
