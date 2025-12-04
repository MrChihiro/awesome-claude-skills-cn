---
name: developer-growth-analysis
description: 分析你最近的 Claude Code 聊天记录，以识别编码模式、开发差距和改进领域，从 HackerNews 策划相关的学习资源，并自动将个性化的成长报告发送到你的 Slack 私信。
---

# 开发者成长分析 (Developer Growth Analysis)

此技能通过分析你的 Claude Code 聊天互动并识别揭示优势和成长领域的模式，为你最近的编码工作提供个性化反馈。

## 何时使用此技能

当你想要执行以下操作时使用此技能：
- 了解你最近工作的开发模式和习惯
- 识别特定的技术差距或反复出现的挑战
- 发现哪些主题将受益于更深入的研究
- 获取根据你的实际工作模式定制的学习资源
- 跟踪你最近项目的改进领域
- 查找直接解决你正在开发的技能的高质量文章

此技能非常适合那些希望在不等待代码审查的情况下获得关于其成长的结构化反馈，并且更喜欢来自自己工作历史的数据驱动见解的开发人员。

## 此技能做什么

此技能对你的开发工作执行六步分析：

1. **读取你的聊天记录**：访问你过去 24-48 小时的本地 Claude Code 聊天记录，以了解你一直在做什么。

2. **识别开发模式**：分析你正在解决的问题类型、你使用的技术、你遇到的挑战以及你如何处理不同类型的任务。

3. **检测改进领域**：识别表明技能差距、重复挣扎、低效方法或你可能受益于更深层知识的领域的模式。

4. **生成个性化报告**：创建一个综合报告，显示你的工作摘要、识别的改进领域和具体的成长建议。

5. **查找学习资源**：使用 HackerNews 策划与你的改进领域直接相关的高质量文章和讨论，为你提供根据你的实际开发工作定制的阅读列表。

6. **发送到你的 Slack 私信**：自动将完整报告发送到你自己的 Slack 直接消息，以便你可以随时随地参考。

## 如何使用

让 Claude 分析你最近的编码工作：

```
Analyze my developer growth from my recent chats
(分析我最近聊天中的开发者成长)
```

或者更具体地说明哪个时间段：

```
Analyze my work from today and suggest areas for improvement
(分析我今天的工作并建议改进领域)
```

该技能将生成一个格式化的报告，其中包含：
- 你最近工作的概述
- 识别的关键改进领域
- 每个领域的具体建议
- 来自 HackerNews 的精选学习资源
- 你可以关注的行动项目

## 指令

当用户请求分析其最近工作的开发者成长或编码模式时：

1. **访问聊天记录**

   从 `~/.claude/history.jsonl` 读取聊天记录。此文件为 JSONL 格式，每行包含：
   - `display`: 用户的消息/请求
   - `project`: 正在进行的项目
   - `timestamp`: Unix 时间戳（以毫秒为单位）
   - `pastedContents`: 任何粘贴的代码或内容

   根据当前时间戳过滤过去 24-48 小时的条目。

2. **分析工作模式**

   从过滤后的聊天中提取并分析以下内容：
   - **项目和领域**：用户正在从事什么类型的项目？（例如，后端、前端、DevOps、数据等）
   - **使用的技术**：对话中出现了哪些语言、框架和工具？
   - **问题类型**：正在解决什么类别的问题？（例如，性能优化、调试、功能实现、重构、设置/配置）
   - **遇到的挑战**：用户在什么问题上挣扎？寻找：
     - 关于类似主题的重复问题
     - 需要多次尝试才能解决的问题
     - 表明知识差距的问题
     - 复杂的架构决策
   - **方法模式**：用户如何解决问题？（例如，有条理的、探索性的、实验性的）

3. **识别改进领域**

   根据分析，确定用户可以改进的 3-5 个特定领域。这些应该是：
   - **具体的**（不是像“提高编码技能”这样模糊的）
   - **基于证据的**（基于实际聊天记录）
   - **可操作的**（可以做出的实际改进）
   - **优先级的**（最有影响力的优先）

   好的改进领域示例：
   - "Advanced TypeScript patterns (generics, utility types, type guards) - you struggled with type safety in [specific project]"
   - "Error handling and validation - I noticed you patched several bugs related to missing null checks"
   - "Async/await patterns - your recent work shows some race conditions and timing issues"
   - "Database query optimization - you rewrote the same query multiple times"

4. **生成报告**

   创建一个具有此结构的综合报告：

   ```markdown
   # Your Developer Growth Report (你的开发者成长报告)

   **Report Period**: [Yesterday / Today / [Custom Date Range]]
   **Last Updated**: [Current Date and Time]

   ## Work Summary (工作摘要)

   [2-3 paragraphs summarizing what the user worked on, projects touched, technologies used, and overall focus areas]

   Example:
   "Over the past 24 hours, you focused primarily on backend development with three distinct projects. Your work involved TypeScript, React, and deployment infrastructure. You tackled a mix of feature implementation, debugging, and architectural decisions, with a particular focus on API design and database optimization."

   ## Improvement Areas (Prioritized) (改进领域（按优先级）)

   ### 1. [Area Name]

   **Why This Matters**: [Explanation of why this skill is important for the user's work]

   **What I Observed**: [Specific evidence from chat history showing this gap]

   **Recommendation**: [Concrete step(s) to improve in this area]

   **Time to Skill Up**: [Brief estimate of effort required]

   ---

   [Repeat for 2-4 additional areas]

   ## Strengths Observed (观察到的优势)

   [2-3 bullet points highlighting things you're doing well - things to continue doing]

   ## Action Items (行动项目)

   Priority order:
   1. [Action item derived from highest priority improvement area]
   2. [Action item from next area]
   3. [Action item from next area]

   ## Learning Resources (学习资源)

   [Will be populated in next step]
   ```

5. **搜索学习资源**

   使用 Rube MCP 在 HackerNews 上搜索与每个改进领域相关的文章：

   - 对于每个改进领域，构建一个针对高质量资源的搜索查询
   - 使用 RUBE_SEARCH_TOOLS 搜索 HackerNews，查询如下：
     - "Learn [Technology/Pattern] best practices"
     - "[Technology] advanced patterns and techniques"
     - "Debugging [specific problem type] in [language]"
   - 优先考虑参与度高（评论、点赞）的帖子
   - 对于每个领域，包括 2-3 篇最相关的文章，包含：
     - 文章标题
     - 发布日期
     - 简要描述为什么它相关
     - 文章链接

   将此部分添加到报告中：

   ```markdown
   ## Curated Learning Resources (精选学习资源)

   ### For: [Improvement Area]

   1. **[Article Title]** - [Date]
      [Description of what it covers and why it's relevant to your improvement area]
      [Link]

   2. **[Article Title]** - [Date]
      [Description]
      [Link]

   [Repeat for other improvement areas]
   ```

6. **呈现完整报告**

   以清晰、可读的格式交付报告，以便用户可以：
   - 快速扫描关键要点
   - 用于重点学习规划
   - 在接下来的一周致力于改进时参考
   - 如果他们想要外部反馈，可以与导师分享

7. **将报告发送到 Slack 私信**

   使用 Rube MCP 将完整报告发送到用户自己的 Slack 私信：

   - 通过 RUBE_SEARCH_TOOLS 检查 Slack 连接是否处于活动状态
   - 如果未连接，使用 RUBE_MANAGE_CONNECTIONS 启动 Slack 认证
   - 使用 RUBE_MULTI_EXECUTE_TOOL 将报告作为格式化消息发送：
     - 发送报告标题和周期作为第一条消息
     - 将报告分解为逻辑部分（摘要、改进、优势、行动、资源）
     - 将每个部分格式化为结构良好的 Slack 消息，带有适当的 markdown
     - 包含学习资源的可点击链接
   - 在 CLI 输出中确认交付

   这确保用户在他们经常检查的地方拥有报告，并可以在整个一周内参考它。

## 示例用法

### 输入

```
Analyze my developer growth from my recent chats
```

### 输出

```markdown
# Your Developer Growth Report

**Report Period**: November 9-10, 2024
**Last Updated**: November 10, 2024, 9:15 PM UTC

## Work Summary

Over the past two days, you focused on backend infrastructure and API development. Your primary project was an open-source showcase application, where you made significant progress on connections management, UI improvements, and deployment configuration. You worked with TypeScript, React, and Node.js, tackling challenges ranging from data security to responsive design. Your work shows a balance between implementing features and addressing technical debt.

## Improvement Areas (Prioritized)

### 1. Advanced TypeScript Patterns and Type Safety

**Why This Matters**: TypeScript is central to your work, but leveraging its advanced features (generics, utility types, conditional types, type guards) can significantly improve code reliability and reduce runtime errors. Better type safety catches bugs at compile time rather than in production.

**What I Observed**: In your recent chats, you were working with connection data structures and struggled a few times with typing auth configurations properly. You also had to iterate on union types for different connection states. There's an opportunity to use discriminated unions and type guards more effectively.

**Recommendation**: Study TypeScript's advanced type system, particularly utility types (Omit, Pick, Record), conditional types, and discriminated unions. Apply these patterns to your connection configuration handling and auth state management.

**Time to Skill Up**: 5-8 hours of focused learning and practice

### 2. Secure Data Handling and Information Hiding in UI

**Why This Matters**: You identified and fixed a security concern where sensitive connection data was being displayed in your console. Preventing information leakage is critical for applications handling user credentials and API keys. Good practices here prevent security incidents and user trust violations.

**What I Observed**: You caught that your "Your Apps" page was showing full connection data including auth configs. This shows good security instincts, and the next step is building this into your default thinking when handling sensitive information.

**Recommendation**: Review security best practices for handling sensitive data in frontend applications. Create reusable patterns for filtering/masking sensitive information before displaying it. Consider implementing a secure data layer that explicitly whitelist what can be shown in the UI.

**Time to Skill Up**: 3-4 hours

### 3. Component Architecture and Responsive UI Patterns

**Why This Matters**: You're designing UIs that need to work across different screen sizes and user interactions. Strong component architecture makes it easier to build complex UIs without bugs and improves maintainability.

**What I Observed**: You worked on the "Marketplace" UI (formerly Browse Tools), recreating it from a design image. You also identified and fixed scrolling issues where content was overflowing containers. There's an opportunity to strengthen your understanding of layout containment and responsive design patterns.

**Recommendation**: Study React component composition patterns and CSS layout best practices (especially flexbox and grid). Focus on container queries and responsive patterns that prevent overflow issues. Look into component composition libraries and design system approaches.

**Time to Skill Up**: 6-10 hours (depending on depth)

## Strengths Observed

- **Security Awareness**: You proactively identified data leakage issues before they became problems
- **Iterative Refinement**: You worked through UI requirements methodically, asking clarifying questions and improving designs
- **Full-Stack Capability**: You comfortably work across backend APIs, frontend UI, and deployment concerns
- **Problem-Solving Approach**: You break down complex tasks into manageable steps

## Action Items

Priority order:
1. Spend 1-2 hours learning TypeScript utility types and discriminated unions; apply to your connection data structures
2. Document security patterns for your project (what data is safe to display, filtering/masking functions)
3. Study one article on advanced React patterns and apply one pattern to your current UI work
4. Set up a code review checklist focused on type safety and data security for future PRs

## Curated Learning Resources

### For: Advanced TypeScript Patterns

1. **TypeScript's Advanced Types: Generics, Utility Types, and Conditional Types** - HackerNews, October 2024
   Deep dive into TypeScript's type system with practical examples and real-world applications. Covers discriminated unions, type guards, and patterns for ensuring compile-time safety in complex applications.
   [Link to discussion]

2. **Building Type-Safe APIs in TypeScript** - HackerNews, September 2024
   Practical guide to designing APIs with TypeScript that catch errors early. Particularly relevant for your connection configuration work.
   [Link to discussion]

### For: Secure Data Handling in Frontend

1. **Preventing Information Leakage in Web Applications** - HackerNews, August 2024
   Comprehensive guide to data security in frontend applications, including filtering sensitive information, secure logging, and audit trails.
   [Link to discussion]

2. **OAuth and API Key Management Best Practices** - HackerNews, July 2024
   How to safely handle authentication tokens and API keys in applications, with examples for different frameworks.
   [Link to discussion]

### For: Component Architecture and Responsive Design

1. **Advanced React Patterns: Composition Over Configuration** - HackerNews
   Explores component composition strategies that scale, with examples using modern React patterns.
   [Link to discussion]

2. **CSS Layout Mastery: Flexbox, Grid, and Container Queries** - HackerNews, October 2024
   Learn responsive design patterns that prevent overflow issues and work across all screen sizes.
   [Link to discussion]
```

## 提示和最佳实践

- 每周运行一次此分析，以跟踪你随时间的改进轨迹
- 一次选择一个改进领域，并在转移到下一个领域之前专注于它几天
- 使用学习资源作为学习指南；完成推荐的材料并练习应用模式
- 在专注于某个领域一周后重新访问此报告，看看你的工作模式如何变化
- 学习资源是为你实际工作精心策划的，而不是通用主题，因此它们将与你正在构建的内容高度相关

## 如何保持准确性和质量

此技能：
- 分析来自带时间戳的聊天记录的实际工作模式
- 生成基于真实项目的循证建议
- 策划直接解决你识别出的差距的学习资源
- 专注于可操作的改进，而不是模糊的反馈
- 根据复杂性提供具体的时间估计
- 优先考虑对你的开发速度影响最大的领域
