# 念念 (NianNian) — AI Agent Guide

## 第一原则：文档同步

**每次对产品功能做任何修改，必须同步更新以下文档：**

- `README.md` — 中文产品文档
- `README.en.md` — 英文产品文档

涉及 UI 变化时还需更新：
- `index.html` 内联的帮助/FAQ 内容
- `CHANGELOG.md`

> 每次 Commit 前自问：这个改动是否改变了用户看得见的行为？→ 是则 README 必须更新。

---

## 产品架构

- **单 HTML 文件**：`index.html` 包含所有 UI、样式、JS 逻辑、农历转换库
- **纯前端**：无后端、无 API、无数据库
- **数据存储**：`localStorage`，Key 为 `niannian_people`
- **部署**：GitHub Pages，提交到 main 分支自动部署

---

## 提醒机制设计（重要）

### 背景

iOS/macOS Calendar App 在导入 ICS 文件时，**会忽略或无法正确处理 VALARM 块**。这是 Apple 的设计限制，不是代码问题。

### 当前方案

**不使用 VALARM**，改为为每个提醒日生成一个**独立的全天日历事件（VEVENT）**。

### 事件标题格式

| 场景 | 格式 | 示例 |
|------|------|------|
| 倒计时提醒 | `{name} · {countdown}` | `爸爸生日 · 3天后` |
| 提前1天 | `{name} · 明天` | `爸爸生日 · 明天` |
| 生日当天 | `🎂 {name}` | `🎂 爸爸生日` |

### 关键函数

- `generateReminderDates(birthdayDate, daysBefore, mode)` — 计算所有提醒日
- `generateICS()` — 对每个提醒日生成一个 VEVENT

### 三种模式

- `once`：仅生日当天一个事件
- `daily`：从提前 N 天到生日，每天一个事件
- `everyOtherDay`：隔天一个事件

---

## 文档更新清单

修改以下内容时，务必同步更新 README：

| 修改内容 | 需更新 |
|---------|--------|
| 提醒机制/模式 | README 提醒模式表格、用户流程 |
| ICS 生成逻辑 | README 技术架构、用户流程 |
| CSV 格式/字段 | README CSV 格式说明 |
| UI 界面/交互 | README 功能特性、用户流程 |
| 新增语言 | README 双语版本 |
| 隐私相关 | PRIVACY.md、README 隐私章节 |
| 版本更新 | CHANGELOG.md |

---

## Commit 规范

```
type:短描述

可选详细说明

- bullet point 说明关键变化
```

type: `feat` / `fix` / `docs` / `refactor` / `style` / `perf`
