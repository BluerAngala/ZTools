# cc-ai-tools

<div align="center">

<img src="./.github/assets/icon.png" alt="cc-ai-tools Logo" width="120">

**高性能、可扩展的应用启动器和插件平台**

[![GitHub release](https://img.shields.io/github/v/release/lawyerch-dev/cc-ai-tools)](https://github.com/lawyerch-dev/cc-ai-tools/releases)
[![License](https://img.shields.io/github/license/lawyerch-dev/cc-ai-tools)](./LICENSE)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-blue)](https://github.com/lawyerch-dev/cc-ai-tools)
[![Docs](https://img.shields.io/badge/docs-online-059669)](https://bluerangala.github.io/cc-ai-tools/)

[English](./README_EN.md) | 简体中文

</div>

---

## 🙏 致谢

本项目 Fork 自 [ZToolsCenter/ZTools](https://github.com/ZToolsCenter/ZTools)，感谢原作者及所有贡献者。

## ✨ 特性

- 🚀 **快速启动** — 拼音搜索、正则匹配、历史记录、固定应用
- 🧩 **插件系统** — UI 插件和无界面插件，完整 API 支持
- 🏪 **多源插件市场** — 官方市场 / GitHub 仓库 / 自定义 CDN，一键切换
- 📋 **剪贴板管理** — 历史记录、搜索、图片支持
- 🎨 **主题定制** — 亮色 / 暗色模式，6 种主题色
- ⚡ **高性能** — LMDB 数据库、WebContentsView 架构
- 🔒 **数据隔离** — 插件数据独立存储

## 🏪 插件市场

支持三种插件来源，在 **设置 → 插件市场 → ⚙️** 中切换：

| 来源            | 说明                                            |
| --------------- | ----------------------------------------------- |
| **官方市场**    | ZTools 官方插件市场，分类齐全                   |
| **GitHub 仓库** | 从 GitHub 扫描 `plugin.json`，支持公开/私有仓库 |
| **CDN 清单**    | 自定义 JSON manifest，灵活部署                  |

### 本项目插件仓库

👉 **[lawyerch-dev/cc-ai-tools-plugins](https://github.com/lawyerch-dev/cc-ai-tools-plugins)**

在设置中选择 **GitHub 仓库**，填入 `lawyerch-dev/cc-ai-tools-plugins`，或选择预设即可。

新增插件：往 `plugins/` 目录加一个含 `plugin.json` 的子目录，推送后市场自动识别。

## 🚀 安装

从 [Releases](https://github.com/lawyerch-dev/cc-ai-tools/releases) 下载：

- **macOS**: `.dmg` 或 `-arm64-mac.zip`
- **Windows**: `-setup.exe` 或 `-win.zip`

### 从源码构建

```bash
git clone https://github.com/lawyerch-dev/cc-ai-tools.git
cd cc-ai-tools
pnpm install
pnpm dev
```

## 💻 开发

```bash
pnpm install          # 安装依赖
pnpm dev              # 开发模式（热重载）
pnpm typecheck        # 类型检查
pnpm build:mac        # 打包 macOS
pnpm build:win        # 打包 Windows
```

## 📄 许可证

[MIT License](./LICENSE)

## 💝 致谢

- [ZToolsCenter/ZTools](https://github.com/ZToolsCenter/ZTools) — 上游项目
- [uTools](https://u.tools/) — 灵感来源
- [Electron](https://www.electronjs.org/) · [Vue.js](https://vuejs.org/) · [LMDB](http://www.lmdb.tech/)
