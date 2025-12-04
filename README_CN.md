<h1 align="center">Awesome Claude Skills (中文版)</h1>

<p align="center">
<a href="https://platform.composio.dev/?utm_source=Github&utm_medium=Youtube&utm_campaign=2025-11&utm_content=AwesomeSkills">
  <img width="1280" height="640" alt="Composio banner" src="https://github.com/user-attachments/assets/adb3f57a-2706-4329-856f-059a32059d48">
</a>


</p>

<p align="center">
  <a href="https://awesome.re">
    <img src="https://awesome.re/badge.svg" alt="Awesome" />
  </a>
  <a href="https://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs Welcome" />
  </a>
  <a href="https://www.apache.org/licenses/LICENSE-2.0">
    <img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg?style=flat-square" alt="License: Apache-2.0" />
  </a>
</p>
<div>
<p align="center">
  <a href="https://twitter.com/composio">
    <img src="https://img.shields.io/badge/Follow on X-000000?style=for-the-badge&logo=x&logoColor=white" alt="Follow on X" />
  </a>
  <a href="https://www.linkedin.com/company/composiohq/">
    <img src="https://img.shields.io/badge/Follow on LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Follow on LinkedIn" />
  </a>
  <a href="https://discord.com/invite/composio">
    <img src="https://img.shields.io/badge/Join our Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Join our Discord" />
  </a>
  </p>
</div>

一份精选的实用 Claude Skills 列表，旨在提升 Claude.ai、Claude Code 和 Claude API 的使用效率。


> 如果你想让你的技能能够跨越 500 多个应用程序执行操作，请使用 [Composio](https://platform.composio.dev/?utm_source=Github&utm_medium=Youtube&utm_campaign=2025-11&utm_content=AwesomeSkills) 进行连接。


## 目录

- [什么是 Claude Skills？](#什么是-claude-skills)
- [技能列表](#技能列表)
  - [文档处理](#文档处理)
  - [开发与代码工具](#开发与代码工具)
  - [数据与分析](#数据与分析)
  - [商业与营销](#商业与营销)
  - [沟通与写作](#沟通与写作)
  - [创意与媒体](#创意与媒体)
  - [生产力与组织](#生产力与组织)
  - [协作与项目管理](#协作与项目管理)
  - [安全与系统](#安全与系统)
- [快速开始](#快速开始)
- [创建技能](#创建技能)
- [贡献](#贡献)
- [资源](#资源)
- [许可证](#许可证)

## 什么是 Claude Skills？

Claude Skills 是可自定义的工作流，用于教导 Claude 如何根据你的特定需求执行特定任务。技能使 Claude 能够在所有 Claude 平台上以可重复、标准化的方式执行任务。

## 技能列表

### 文档处理

- [docx](https://github.com/anthropics/skills/tree/main/document-skills/docx) - 创建、编辑和分析 Word 文档，支持修订、批注和格式设置。
- [pdf](https://github.com/anthropics/skills/tree/main/document-skills/pdf) - 提取文本、表格、元数据，合并及注释 PDF。
- [pptx](https://github.com/anthropics/skills/tree/main/document-skills/pptx) - 读取、生成和调整幻灯片、布局及模板。
- [xlsx](https://github.com/anthropics/skills/tree/main/document-skills/xlsx) - 电子表格操作：公式、图表、数据转换。
- [Markdown to EPUB Converter](https://github.com/smerchek/claude-epub-skill) - 将 Markdown 文档和聊天摘要转换为专业的 EPUB 电子书文件。*作者：[@smerchek](https://github.com/smerchek)*

### 开发与代码工具

- [artifacts-builder](https://github.com/anthropics/skills/tree/main/web-artifacts-builder) - 一套用于使用现代前端 Web 技术（React, Tailwind CSS, shadcn/ui）创建精细的多组件 claude.ai HTML artifacts 的工具。
- [aws-skills](https://github.com/zxkane/aws-skills) - 包含 CDK 最佳实践、成本优化 MCP 服务器以及无服务器/事件驱动架构模式的 AWS 开发工具。
- [Changelog Generator](./changelog-generator/) - 通过分析 git 提交历史，将技术提交转换为对客户友好的发布说明，自动创建面向用户的更新日志。
- [Claude Code Terminal Title](https://github.com/bluzername/claude-code-terminal-title) - 为每个 Claude-Code 终端窗口提供动态标题，描述正在进行的工作，防止你迷失在多个窗口中。
- [D3.js Visualization](https://github.com/chrisvoncsefalvay/claude-d3js-skill) - 教导 Claude 生成 D3 图表和交互式数据可视化。*作者：[@chrisvoncsefalvay](https://github.com/chrisvoncsefalvay)*
- [FFUF Web Fuzzing](https://github.com/jthack/ffuf_claude_skill) - 集成 ffuf web 模糊测试工具，使 Claude 能够运行模糊测试任务并分析漏洞结果。*作者：[@jthack](https://github.com/jthack)*
- [finishing-a-development-branch](https://github.com/obra/superpowers/tree/main/skills/finishing-a-development-branch) - 通过提供清晰的选项和处理选定的工作流，指导完成开发工作。
- [iOS Simulator](https://github.com/conorluddy/ios-simulator-skill) - 使 Claude 能够与 iOS 模拟器交互，用于测试和调试 iOS 应用程序。*作者：[@conorluddy](https://github.com/conorluddy)*
- [MCP Builder](./mcp-builder/) - 指导使用 Python 或 TypeScript 创建高质量的 MCP (Model Context Protocol) 服务器，以便将外部 API 和服务与 LLM 集成。
- [move-code-quality-skill](https://github.com/1NickPappas/move-code-quality-skill) - 根据官方 Move Book 代码质量清单分析 Move 语言包，确保符合 Move 2024 版本规范和最佳实践。
- [Playwright Browser Automation](https://github.com/lackeyjb/playwright-skill) - 模型调用的 Playwright 自动化工具，用于测试和验证 Web 应用程序。*作者：[@lackeyjb](https://github.com/lackeyjb)*
- [prompt-engineering](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/customaize-agent/skills/prompt-engineering) - 教授著名的提示工程技术和模式，包括 Anthropic 最佳实践和智能体说服原则。
- [pypict-claude-skill](https://github.com/omkamal/pypict-claude-skill) - 使用 PICT (Pairwise Independent Combinatorial Testing) 为需求 or 代码设计全面的测试用例，生成具有成对覆盖率的优化测试套件。
- [Skill Creator](./skill-creator/) - 提供创建有效 Claude Skills 的指导，通过专业知识、工作流和工具集成扩展能力。
- [Skill Seekers](https://github.com/yusufkaraaslan/Skill_Seekers) - 在几分钟内自动将任何文档网站转换为 Claude AI 技能。*作者：[@yusufkaraaslan](https://github.com/yusufkaraaslan)*
- [software-architecture](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/ddd/skills/software-architecture) - 实施设计模式，包括整洁架构 (Clean Architecture)、SOLID 原则和全面的软件设计最佳实践。
- [subagent-driven-development](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/sadd/skills/subagent-driven-development) - 为单个任务分派独立的子智能体，并在迭代之间进行代码审查检查点，以实现快速、受控的开发。
- [test-driven-development](https://github.com/obra/superpowers/tree/main/skills/test-driven-development) - 在编写实现代码之前，用于实现任何功能或修复 bug 时使用。
- [using-git-worktrees](https://github.com/obra/superpowers/blob/main/skills/using-git-worktrees/) - 创建具有智能目录选择和安全验证的隔离 git worktrees。
- [Webapp Testing](./webapp-testing/) - 使用 Playwright 测试本地 Web 应用程序，用于验证前端功能、调试 UI 行为和捕获屏幕截图。

### 数据与分析

- [CSV Data Summarizer](https://github.com/coffeefuelbump/csv-data-summarizer-claude-skill) - 自动分析 CSV 文件并生成包含可视化的全面见解，无需用户提示。*作者：[@coffeefuelbump](https://github.com/coffeefuelbump)*
- [root-cause-tracing](https://github.com/obra/superpowers/tree/main/skills/root-cause-tracing) - 当错误发生在执行深处，你需要回溯以找到原始触发点时使用。

### 商业与营销

- [Brand Guidelines](./brand-guidelines/) - 将 Anthropic 的官方品牌颜色和排版应用于 artifact，以保持一致的视觉识别和专业设计标准。
- [Competitive Ads Extractor](./competitive-ads-extractor/) - 从广告库中提取并分析竞争对手的广告，以了解产生共鸣的信息和创意方法。
- [Domain Name Brainstormer](./domain-name-brainstormer/) - 生成创意域名构想，并检查包括 .com, .io, .dev 和 .ai 在内的多个顶级域名的可用性。
- [Internal Comms](./internal-comms/) - 协助编写内部沟通内容，包括第三方更新、公司通讯、常见问题解答、状态报告和项目更新，使用公司特定格式。
- [Lead Research Assistant](./lead-research-assistant/) - 通过分析你的产品、搜索目标公司并提供可行的外联策略，识别和筛选高质量的潜在客户。

### 沟通与写作

- [article-extractor](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/article-extractor) - 从网页中提取完整的文章文本和元数据。
- [brainstorming](https://github.com/obra/superpowers/tree/main/skills/brainstorming) - 通过结构化提问和替代方案探索，将粗略的想法转化为完全成型的设计。
- [Content Research Writer](./content-research-writer/) - 通过进行研究、添加引用、改进吸引点和提供逐节反馈，协助编写高质量内容。
- [family-history-research](https://github.com/emaynard/claude-family-history-research-skill) - 为规划家族史和家谱研究项目提供帮助。
- [Meeting Insights Analyzer](./meeting-insights-analyzer/) - 分析会议记录以揭示行为模式，包括避免冲突、发言比例、填充词和领导风格。
- [NotebookLM Integration](https://github.com/PleasePrompto/notebooklm-skill) - 让 Claude Code 直接与 NotebookLM 对话，仅基于上传的文档提供有来源依据的答案。*作者：[@PleasePrompto](https://github.com/PleasePrompto)*

### 创意与媒体

- [Canvas Design](./canvas-design/) - 使用设计哲学和美学原则为海报、设计和静态作品创建精美的 PNG 和 PDF 视觉艺术。
- [Image Enhancer](./image-enhancer/) - 通过提高分辨率、锐度和清晰度来改善图像和屏幕截图质量，用于专业演示和文档。
- [Slack GIF Creator](./slack-gif-creator/) - 创建针对 Slack 优化的动画 GIF，带有大小限制验证器和可组合的动画原语。
- [Theme Factory](./theme-factory/) - 将专业字体和颜色主题应用于 artifact，包括幻灯片、文档、报告和 HTML 落地页，提供 10 种预设主题。
- [Video Downloader](./video-downloader/) - 从 YouTube 和其他平台下载视频，用于离线观看、编辑或存档，支持多种格式和质量选项。
- [youtube-transcript](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/youtube-transcript) - 获取 YouTube 视频的字幕并准备摘要。

### 生产力与组织

- [File Organizer](./file-organizer/) - 通过理解上下文、查找重复项并建议更好的组织结构，智能地组织文件和文件夹。
- [Invoice Organizer](./invoice-organizer/) - 通过读取文件、提取信息和一致重命名，自动组织发票和收据以备税务准备。
- [kaizen](https://github.com/NeoLabHQ/context-engineering-kit/tree/master/plugins/kaizen/skills/kaizen) - 基于日本改善 (Kaizen) 哲学和精益方法论，应用多种分析方法的持续改进方法。
- [n8n-skills](https://github.com/haunchen/n8n-skills) - 使 AI 助手能够直接理解和操作 n8n 工作流。
- [Raffle Winner Picker](./raffle-winner-picker/) - 从列表、电子表格或 Google Sheets 中随机选择赠品和竞赛的获胜者，具有加密安全的随机性。
- [ship-learn-next](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/ship-learn-next) - 基于反馈循环帮助迭代下一步构建或学习内容的技能。
- [tapestry](https://github.com/michalparkola/tapestry-skills-for-claude-code/tree/main/tapestry) - 将相关文档互连并总结为知识网络。

### 协作与项目管理

- [git-pushing](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/engineering-workflow-plugin/skills/git-pushing) - 自动化 git 操作和仓库交互。
- [review-implementing](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/engineering-workflow-plugin/skills/review-implementing) - 评估代码实施计划并与规范保持一致。
- [test-fixing](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/engineering-workflow-plugin/skills/test-fixing) - 检测失败的测试并提出补丁或修复建议。

### 安全与系统

- [computer-forensics](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/computer-forensics-skills/skills/computer-forensics) - 数字取证分析和调查技术。
- [file-deletion](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/computer-forensics-skills/skills/file-deletion) - 安全文件删除和数据清理方法。
- [metadata-extraction](https://github.com/mhattingpete/claude-skills-marketplace/tree/main/computer-forensics-skills/skills/metadata-extraction) - 为取证目的提取和分析文件元数据。
- [threat-hunting-with-sigma-rules](https://github.com/jthack/threat-hunting-with-sigma-rules-skill) - 使用 Sigma 检测规则搜寻威胁并分析安全事件。

## 快速开始

### 在 Claude.ai 中使用技能

1. 点击聊天界面中的技能图标 (🧩)。
2. 从市场添加技能或上传自定义技能。
3. Claude 会根据你的任务自动激活相关技能。

### 在 Claude Code 中使用技能

1. 将技能放置在 `~/.config/claude-code/skills/` 目录下：
   ```bash
   mkdir -p ~/.config/claude-code/skills/
   cp -r skill-name ~/.config/claude-code/skills/
   ```

2. 验证技能元数据：
   ```bash
   head ~/.config/claude-code/skills/skill-name/SKILL.md
   ```

3. 启动 Claude Code：
   ```bash
   claude
   ```

4. 技能会自动加载并在相关时激活。

### 通过 API 使用技能

使用 Claude Skills API 编程方式加载和管理技能：

```python
import anthropic

client = anthropic.Anthropic(api_key="your-api-key")

response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    skills=["skill-id-here"],
    messages=[{"role": "user", "content": "Your prompt"}]
)
```

详情请参阅 [Skills API 文档](https://docs.claude.com/en/api/skills-guide)。

## 创建技能

### 技能结构

每个技能都是一个包含 `SKILL.md` 文件（带有 YAML frontmatter）的文件夹：

```
skill-name/
├── SKILL.md          # 必需：技能说明和元数据
├── scripts/          # 可选：辅助脚本
├── templates/        # 可选：文档模板
└── resources/        # 可选：参考文件
```

### 基本技能模板

```markdown
---
name: my-skill-name
description: 清晰描述此技能的作用以及何时使用它。
---

# My Skill Name

详细描述技能的目的和能力。

## When to Use This Skill (何时使用此技能)

- 用例 1
- 用例 2
- 用例 3

## Instructions (指令)

[给 Claude 的关于如何执行此技能的详细指令]

## Examples (示例)

[展示技能实际运作的真实示例]
```

### 技能最佳实践

- 专注于具体的、可重复的任务
- 包含清晰的示例和边缘情况
- 为 Claude 编写指令，而不是为最终用户
- 在 Claude.ai、Claude Code 和 API 上进行测试
- 记录先决条件和依赖关系
- 包含错误处理指南

## 贡献

我们欢迎贡献！请阅读我们的 [贡献指南](CONTRIBUTING.md) 了解详情：

- 如何提交新技能
- 技能质量标准
- Pull request 流程
- 行为准则

### 快速贡献步骤

1. 确保你的技能基于真实用例
2. 检查现有技能中是否有重复
3. 遵循技能结构模板
4. 跨平台测试你的技能
5. 提交带有清晰文档的 pull request

## 资源

### 官方文档

- [Claude Skills 概览](https://www.anthropic.com/news/skills) - 官方公告和特性
- [Skills 用户指南](https://support.claude.com/en/articles/12512180-using-skills-in-claude) - 如何在 Claude 中使用技能
- [创建自定义 Skills](https://support.claude.com/en/articles/12512198-creating-custom-skills) - 技能开发指南
- [Skills API 文档](https://docs.claude.com/en/api/skills-guide) - API 集成指南
- [Agent Skills 博客文章](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) - 工程深度解析

### 社区资源

- [Anthropic Skills 仓库](https://github.com/anthropics/skills) - 官方示例技能
- [Claude 社区](https://community.anthropic.com) - 与其他用户讨论技能
- [Skills 市场](https://claude.ai/marketplace) - 发现并分享技能

### 灵感与用例

- [Lenny's Newsletter](https://www.lennysnewsletter.com/p/everyone-should-be-using-claude-code) - 人们使用 Claude Code 的 50 种方式
- [Notion Skills](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0) - Notion 集成技能


## 加入社区

- 对将 Composio 与你的认证设置集成有疑问？[与我们进行快速通话](https://calendly.com/thomas-composio/composio-enterprise-setup)
- [在 Twitter 上关注我们](https://x.com/composio)
- [加入我们的 Discord](https://discord.com/invite/composio)

## 许可证

本仓库根据 Apache License 2.0 授权。

个别技能可能具有不同的许可证 - 请检查每个技能的文件夹以获取特定的许可信息。

---

**注意**：Claude Skills 适用于 Claude.ai、Claude Code 和 Claude API。一旦你创建了一个技能，它就可以在所有平台上移植，使你的工作流在你使用 Claude 的任何地方都保持一致。
