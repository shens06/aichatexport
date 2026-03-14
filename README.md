# AI Chat Manager / AI聊天记录管家

> 一款轻量、开箱即用的 AI 聊天记录管理工具，支持多平台导入、全文搜索与导出。
> A lightweight, ready-to-use AI chat history manager with multi-platform import, full-text search, and export.

---

## Screenshots / 截图

> *(Add your screenshots here / 在此添加截图)*

---

## Features / 功能特性

| Feature | 功能 |
|---------|------|
| Multi-platform import (ChatGPT, Claude, DeepSeek, Gemini, Doubao, Kimi) | 多平台导入（ChatGPT、Claude、DeepSeek、Gemini、豆包、Kimi） |
| Auto platform detection from file name & structure | 自动识别平台（文件名+数据结构双重判断） |
| Full-text search across all conversations | 全文搜索，覆盖所有对话内容 |
| Filter by date: Today / This Week / This Month | 按时间筛选：今天 / 本周 / 本月 |
| Favorites with persistent storage | 收藏夹，数据持久化保存 |
| Export single conversation as `.txt` | 导出单条对话为 `.txt` 文件 |
| Batch export all visible conversations as `.zip` | 批量导出全部对话为 `.zip` 压缩包 |
| Conversation summary & statistics | 对话摘要与统计信息 |
| Copy all messages to clipboard | 一键复制全部消息到剪贴板 |
| Print preview | 打印预览 |
| Resizable 3-column layout | 可拖动三栏布局 |
| PyInstaller packaging compatible | 兼容 PyInstaller 打包为 exe |

---

## Supported Platforms / 支持的平台

| Platform | Export Format |
|----------|---------------|
| ChatGPT (OpenAI) | `conversations.json` (official export) |
| Claude (Anthropic) | `claude_data.json` / threads JSON |
| DeepSeek | DeepSeek export JSON |
| Gemini (Google) | Gemini export JSON |
| Doubao (豆包) | Doubao export JSON |
| Kimi (Moonshot) | Kimi export JSON |

---

## Requirements / 运行环境

- Python 3.8+
- Standard library only — **no third-party packages required**
  仅使用标准库，**无需安装任何第三方依赖**

---

## Usage / 使用方法

### Run directly / 直接运行

**Chinese UI / 中文界面:**
```bash
python aichatexport
```

**English UI / 英文界面:**
```bash
python aichatexport_en
```

### Package as executable / 打包为 exe

Install PyInstaller first / 先安装 PyInstaller:
```bash
pip install pyinstaller
```

Package / 打包:
```bash
# Chinese UI / 中文界面
pyinstaller --onefile --windowed --name aichatexport aichatexport

# English UI / 英文界面
pyinstaller --onefile --windowed --name aichatexport_en aichatexport_en
```

The output `.exe` will be in the `dist/` folder.
生成的 `.exe` 文件在 `dist/` 目录中。

---

## Data Storage / 数据存储

| Item | Location | Description |
|------|----------|-------------|
| Favorites | `aichatexport_settings.json` (same directory as the program) | Stores favorited conversation IDs only |
| Chat content | Your original imported JSON files | Not copied or stored separately |

> **Note / 注意:** Favorites only store conversation IDs. If you remove or replace the source JSON files, favorited entries will no longer be found.
> 收藏夹只保存对话 ID，不保存聊天内容本身。删除或替换原始 JSON 文件后，收藏夹中的对话将无法找到。

---

## File Structure / 文件结构

```
aichatexport/
├── aichatexport          # Main app - Chinese UI / 中文界面
├── aichatexport_en       # English UI / 英文界面
└── aichatexport_settings.json   # Auto-generated on first run / 首次运行自动生成
```

---

## How to Export Chat History / 如何导出聊天记录

<details>
<summary>ChatGPT</summary>

1. Go to **Settings → Data controls → Export data**
   前往 **设置 → 数据控制 → 导出数据**
2. Wait for the email and download the ZIP
   等待邮件并下载 ZIP
3. Extract and use `conversations.json`
   解压后使用 `conversations.json`

</details>

<details>
<summary>Claude</summary>

1. Go to **Settings → Privacy → Export data**
   前往 **设置 → 隐私 → 导出数据**
2. Download and extract the ZIP
   下载并解压 ZIP
3. Use the JSON file inside
   使用其中的 JSON 文件

</details>

<details>
<summary>DeepSeek / Gemini / Doubao / Kimi</summary>

Use the official export feature in each platform's settings.
使用各平台设置中的官方导出功能。

</details>

---

## License / 许可证

MIT License
