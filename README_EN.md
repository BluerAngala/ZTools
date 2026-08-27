# cc-ai-tools

<div align="center">

<img src="./.github/assets/icon.png" alt="cc-ai-tools Logo" width="120">

**High-performance, extensible application launcher and plugin platform**

[![GitHub release](https://img.shields.io/github/v/release/lawyerch-dev/cc-ai-tools)](https://github.com/lawyerch-dev/cc-ai-tools/releases)
[![License](https://img.shields.io/github/license/lawyerch-dev/cc-ai-tools)](./LICENSE)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-blue)](https://github.com/lawyerch-dev/cc-ai-tools)

English | [简体中文](./README.md)

</div>

---

## 🙏 Credits

Forked from [ZToolsCenter/ZTools](https://github.com/ZToolsCenter/ZTools). Thanks to the original authors and all contributors.

## ✨ Features

- 🚀 **Fast Launch** — Pinyin search, regex matching, history, pinned apps
- 🧩 **Plugin System** — UI and headless plugins with full API support
- 🏪 **Multi-Source Plugin Market** — Official / GitHub / Custom CDN, switch with one click
- 📋 **Clipboard Manager** — History, search, image support
- 🎨 **Themes** — Light / Dark mode, 6 accent colors
- ⚡ **High Performance** — LMDB database, WebContentsView architecture
- 🔒 **Data Isolation** — Independent plugin storage

## 🏪 Plugin Market

Three plugin sources, configurable in **Settings → Plugin Market → ⚙️**:

| Source       | Description                             |
| ------------ | --------------------------------------- |
| **Official** | ZTools official market                  |
| **GitHub**   | Scan `plugin.json` from any GitHub repo |
| **CDN**      | Custom JSON manifest                    |

### Plugin Repository

👉 **[lawyerch-dev/cc-ai-tools-plugins](https://github.com/lawyerch-dev/cc-ai-tools-plugins)**

Select **GitHub** in settings, enter `lawyerch-dev/cc-ai-tools-plugins`, or use the preset.

## 🚀 Install

Download from [Releases](https://github.com/lawyerch-dev/cc-ai-tools/releases):

- **macOS**: `.dmg` or `-arm64-mac.zip`
- **Windows**: `-setup.exe` or `-win.zip`

### Build from Source

```bash
git clone https://github.com/lawyerch-dev/cc-ai-tools.git
cd cc-ai-tools
pnpm install
pnpm dev
```

## 📄 License

[MIT License](./LICENSE)

## 💝 Credits

- [ZToolsCenter/ZTools](https://github.com/ZToolsCenter/ZTools) — Upstream
- [uTools](https://u.tools/) — Inspiration
- [Electron](https://www.electronjs.org/) · [Vue.js](https://vuejs.org/) · [LMDB](http://www.lmdb.tech/)
