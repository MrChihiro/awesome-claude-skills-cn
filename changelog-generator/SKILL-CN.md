---
name: changelog-generator
description: 通过分析提交历史、分类更改并将技术提交转换为清晰、客户友好的发布说明，自动从 git 提交创建面向用户的更新日志。将数小时的手动更新日志编写工作转化为几分钟的自动生成。
---

# 更新日志生成器 (Changelog Generator)

此技能将技术 git 提交转换为精美的、用户友好的更新日志，让你的客户和用户真正理解并欣赏。

## 何时使用此技能

- 准备新版本的发布说明
- 创建每周或每月的产​​品更新摘要
- 为客户记录更改
- 为应用商店提交编写更新日志条目
- 生成更新通知
- 创建内部发布文档
- 维护公开的更新日志/产品更新页面

## 此技能做什么

1. **扫描 Git 历史**：分析特定时间段内或版本之间的提交
2. **分类更改**：将提交分组为逻辑类别（功能、改进、错误修复、破坏性更改、安全）
3. **翻译技术 → 用户友好**：将开发人员提交转换为客户语言
4. **专业格式化**：创建整洁、结构化的更新日志条目
5. **过滤噪音**：排除内部提交（重构、测试等）
6. **遵循最佳实践**：应用更新日志指南和你的品牌声音

## 如何使用

### 基本用法

从你的项目仓库：

```
Create a changelog from commits since last release
(从上次发布以来的提交创建一个更新日志)
```

```
Generate changelog for all commits from the past week
(为过去一周的所有提交生成更新日志)
```

```
Create release notes for version 2.5.0
(为版本 2.5.0 创建发布说明)
```

### 指定日期范围

```
Create a changelog for all commits between March 1 and March 15
(为 3 月 1 日至 3 月 15 日之间的所有提交创建一个更新日志)
```

### 使用自定义指南

```
Create a changelog for commits since v2.4.0, using my changelog 
guidelines from CHANGELOG_STYLE.md
(自 v2.4.0 以来的提交创建一个更新日志，使用我 CHANGELOG_STYLE.md 中的更新日志指南)
```

## 示例

**用户**: "Create a changelog for commits from the past 7 days" (为过去 7 天的提交创建一个更新日志)

**输出**:
```markdown
# Updates - Week of March 10, 2024

## ✨ New Features (新功能)

- **Team Workspaces**: Create separate workspaces for different 
  projects. Invite team members and keep everything organized.
  (团队工作区：为不同项目创建单独的工作区。邀请团队成员并保持一切井井有条。)

- **Keyboard Shortcuts**: Press ? to see all available shortcuts. 
  Navigate faster without touching your mouse.
  (键盘快捷键：按 ? 查看所有可用快捷键。无需触摸鼠标即可更快导航。)

## 🔧 Improvements (改进)

- **Faster Sync**: Files now sync 2x faster across devices
  (更快的同步：文件现在在设备间同步速度快 2 倍)
- **Better Search**: Search now includes file contents, not just titles
  (更好的搜索：搜索现在包含文件内容，而不仅仅是标题)

## 🐛 Fixes (修复)

- Fixed issue where large images wouldn't upload
  (修复了大图像无法上传的问题)
- Resolved timezone confusion in scheduled posts
  (解决了预定帖子中的时区混淆)
- Corrected notification badge count
  (更正了通知徽章计数)
```

**灵感来源:** Lenny's Newsletter 中 Manik Aggarwal 的用例

## 提示

- 从你的 git 仓库根目录运行
- 为特定更新日志指定日期范围
- 使用你的 CHANGELOG_STYLE.md 进行一致的格式化
- 在发布之前查看并调整生成的更新日志
- 将输出直接保存到 CHANGELOG.md

## 相关用例

- 创建 GitHub 发布说明
- 编写应用商店更新描述
- 为用户生成电子邮件更新
- 创建社交媒体公告帖子
