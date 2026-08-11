# 插件开发文档

## 目录结构

```
my-plugin/
├── plugin.json        # 插件配置（必须）
├── index.html         # 入口页面（UI 插件必须）
├── logo.png           # 插件图标（推荐 120x120）
├── preload.js         # preload 脚本（可选）
└── ...                # 其他资源
```

## plugin.json

```json
{
  "name": "my-plugin",
  "title": "我的插件",
  "description": "插件描述",
  "version": "1.0.0",
  "author": "作者",
  "main": "index.html",
  "logo": "logo.png",
  "preload": "preload.js",
  "homepage": "https://github.com/...",
  "platform": ["darwin", "win32"],
  "features": [
    {
      "code": "my-command",
      "explain": "命令说明",
      "icon": "logo.png",
      "cmds": ["关键词1", "关键词2", { "type": "over", "label": "实时搜索", "minLength": 1 }]
    }
  ]
}
```

### 字段说明

| 字段          | 必填 | 说明                              |
| ------------- | ---- | --------------------------------- |
| `name`        | ✅   | 唯一标识，建议与目录名一致        |
| `title`       | ✅   | 显示名称                          |
| `version`     | ✅   | 语义化版本 `x.y.z`                |
| `main`        | ✅   | 入口 HTML，无界面插件可省略       |
| `features`    | ✅   | 功能指令列表                      |
| `description` |      | 描述文字                          |
| `author`      |      | 作者                              |
| `logo`        |      | 图标路径（相对插件目录）          |
| `preload`     |      | preload 脚本路径                  |
| `homepage`    |      | 项目主页 URL                      |
| `platform`    |      | 限定平台 `["darwin"]` `["win32"]` |

### features 指令

```json
{
  "code": "open-settings",
  "explain": "打开设置",
  "icon": "logo.png",
  "cmds": ["设置", "settings"]
}
```

- `code` — 指令标识，用户选择时传入插件
- `explain` — 指令说明
- `cmds` — 触发关键词，支持字符串和高级匹配对象

#### 高级匹配（over 模式）

实时接收用户输入，适合搜索类插件：

```json
{ "type": "over", "label": "翻译", "minLength": 1, "maxLength": 200 }
```

## API

插件通过 `window.ztools` 对象调用宿主能力。

### 基础

```js
// 获取应用版本
window.ztools.getVersion()

// 退出插件
window.ztools.outPlugin()
```

### 剪贴板

```js
// 读取剪贴板文本
const text = window.ztools.getClipboardText()

// 写入剪贴板
window.ztools.setClipboardText('hello')
```

### 通知

```js
window.ztools.showNotification({
  title: '标题',
  content: '内容',
  clickFeatureCode: 'my-command' // 点击后打开的指令
})
```

### 数据存储

```js
// 存储（插件数据隔离，不会互相干扰）
window.ztools.dbStorage.setItem('key', { value: 42 })

// 读取
const data = window.ztools.dbStorage.getItem('key')

// 删除
window.ztools.dbStorage.removeItem('key')
```

### 事件

```js
// 监听指令进入
window.ztools.onPluginEnter(({ code, type, payload }) => {
  // code — feature.code
  // type — 'over' | 'text' | ...
  // payload — 用户输入
})

// 监听窗口显示/隐藏
window.ztools.onPluginShow(() => {
  /* 显示 */
})
window.ztools.onPluginHide(() => {
  /* 隐藏 */
})
```

### 子窗口

```js
// 打开独立窗口
window.ztools.createBrowserWindow({
  url: 'detail.html',
  width: 600,
  height: 400,
  title: '详情'
})
```

## 开发流程

### 1. 本地开发

在 cc-ai-tools 设置 → 插件管理 → **添加开发中插件**，选择插件目录即可实时开发。

### 2. 打包发布

```bash
# 在设置 → 开发项目 → 打包为 .zpx
# 或使用 ztools-plugin-cli
```

### 3. 上架市场

将插件目录提交到 [cc-ai-tools-plugins](https://github.com/BluerAngala/cc-ai-tools-plugins) 仓库：

```
plugins/
  my-plugin/
    plugin.json
    index.html
    logo.png
    README.md      # 插件介绍文档
```

推送后，用户在插件市场选择 **GitHub 仓库** 源即可看到你的插件。

## 示例

参考 [hello-world](https://github.com/BluerAngala/cc-ai-tools-plugins/tree/main/plugins/hello-world) 示例插件。
