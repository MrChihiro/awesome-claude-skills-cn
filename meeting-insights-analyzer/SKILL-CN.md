---
name: meeting-insights-analyzer
description: 分析会议记录和录音，以发现行为模式、沟通见解和可操作的反馈。识别你何时避免冲突、使用填充词、主导对话或错失倾听机会。非常适合寻求提高沟通和领导技能的专业人士。
---

# 会议见解分析器 (Meeting Insights Analyzer)

此技能将你的会议记录转化为关于你沟通模式的可操作见解，帮助你成为更有效的沟通者和领导者。

## 何时使用此技能

- 分析你在多次会议中的沟通模式
- 获取关于你的领导和引导风格的反馈
- 识别你何时避免困难的对话
- 了解你的说话习惯和填充词
- 跟踪沟通技能随时间的改进
- 准备带有具体示例的绩效评估
- 指导团队成员的沟通风格

## 此技能做什么

1. **模式识别**：识别跨会议的重复行为，如：
   - 冲突避免或间接沟通
   - 说话比例和轮流发言
   - 提问与陈述模式
   - 积极倾听指标
   - 决策方法

2. **沟通分析**：评估沟通有效性：
   - 清晰度和直接性
   - 填充词和模糊语言的使用
   - 语气和情绪模式
   - 会议控制和引导

3. **可操作的反馈**：提供具体的、带时间戳的示例：
   - 发生了什么
   - 为什么这很重要
   - 如何改进

4. **趋势跟踪**：在分析多次会议时比较随时间变化的模式

## 如何使用

### 基本设置

1. 将你的会议记录下载到一个文件夹（例如 `~/meetings/`）
2. 在 Claude Code 中导航到该文件夹
3. 请求你想要的分析

### 快速入门示例

```
Analyze all meetings in this folder and tell me when I avoided conflict.
(分析此文件夹中的所有会议，并告诉我何时我避免了冲突。)
```

```
Look at my meetings from the past month and identify my communication patterns.
(查看我过去一个月的会议并识别我的沟通模式。)
```

```
Compare my facilitation style between these two meeting folders.
(比较这两个会议文件夹之间的引导风格。)
```

### 高级分析

```
Analyze all transcripts in this folder and:
1. Identify when I interrupted others
2. Calculate my speaking ratio
3. Find moments I avoided giving direct feedback
4. Track my use of filler words
5. Show examples of good active listening
(分析此文件夹中的所有记录并：
1. 识别我何时打断他人
2. 计算我的说话比例
3. 找到我避免给予直接反馈的时刻
4. 跟踪我对填充词的使用
5. 展示良好的积极倾听示例)
```

## 指令

当用户请求会议分析时：

1. **发现可用数据**
   - 扫描文件夹以查找记录文件 (.txt, .md, .vtt, .srt, .docx)
   - 检查文件是否包含演讲者标签和时间戳
   - 确认会议的日期范围
   - 在记录中识别用户的姓名/标识符

2. **澄清分析目标**
   
   如果未指定，询问他们想了解什么：
   - 具体行为（冲突避免、打断、填充词）
   - 沟通有效性（清晰度、直接性、倾听）
   - 会议引导技能
   - 说话模式和比例
   - 改进的增长领域
   
3. **分析模式**

   对于每个请求的见解：
   
   **冲突避免**：
   - 寻找模糊语言（"maybe", "kind of", "I think"）
   - 间接措辞而不是直接请求
   - 当紧张局势出现时改变话题
   - 没有承诺的同意（"yeah, but..."）
   - 不解决明显的问题
   
   **说话比例**：
   - 计算会议中说话的百分比
   - 计数打断（由用户和对用户）
   - 测量平均说话轮次长度
   - 跟踪提问与陈述的比例
   
   **填充词**：
   - 计数 "um", "uh", "like", "you know", "actually" 等
   - 注意每分钟或每次发言的频率
   - 识别它们增加的情况（紧张、不确定）
   
   **积极倾听**：
   - 引用他人先前观点的提问
   - 解释或总结他人的想法
   - 建立在他人的贡献之上
   - 提出澄清问题
   
   **领导与引导**：
   - 决策方法（指令性 vs. 协作性）
   - 如何处理分歧
   - 包含更安静的参与者
   - 时间管理和议程控制
   - 后续行动和行动项目的清晰度

4. **提供具体示例**

   对于发现的每个模式，包括：
   
   ```markdown
   ### [Pattern Name]
   
   **Finding**: [One-sentence summary of the pattern]
   
   **Frequency**: [X times across Y meetings]
   
   **Examples**:
   
   1. **[Meeting Name/Date]** - [Timestamp]
      
      **What Happened**:
      > [Actual quote from transcript]
      
      **Why This Matters**:
      [Explanation of the impact or missed opportunity]
      
      **Better Approach**:
      [Specific alternative phrasing or behavior]
   
   [Repeat for 2-3 strongest examples]
   ```

5. **综合见解**

   分析所有模式后，提供：
   
   ```markdown
   # Meeting Insights Summary
   
   **Analysis Period**: [Date range]
   **Meetings Analyzed**: [X meetings]
   **Total Duration**: [X hours]
   
   ## Key Patterns Identified
   
   ### 1. [Primary Pattern]
   - **Observed**: [What you saw]
   - **Impact**: [Why it matters]
   - **Recommendation**: [How to improve]
   
   ### 2. [Second Pattern]
   [Same structure]
   
   ## Communication Strengths
   
   1. [Strength 1 with example]
   2. [Strength 2 with example]
   3. [Strength 3 with example]
   
   ## Growth Opportunities
   
   1. **[Area 1]**: [Specific, actionable advice]
   2. **[Area 2]**: [Specific, actionable advice]
   3. **[Area 3]**: [Specific, actionable advice]
   
   ## Speaking Statistics
   
   - Average speaking time: [X% of meeting]
   - Questions asked: [X per meeting average]
   - Filler words: [X per minute]
   - Interruptions: [X given / Y received per meeting]
   
   ## Next Steps
   
   [3-5 concrete actions to improve communication]
   ```

6. **提供后续选项**
   - 在未来的会议中跟踪这些相同的指标
   - 深入研究特定会议或模式
   - 与行业基准进行比较
   - 创建个人沟通发展计划
   - 为绩效评估生成摘要

## 示例

### 示例 1: 冲突避免分析 (灵感来自 Dan Shipper)

**用户**: "I download all of my meeting recordings and put them in a folder. Tell me all the times I've subtly avoided conflict." (我下载了我所有的会议录音并将它们放在一个文件夹中。告诉我所有我微妙地避免冲突的时候。)

**输出**: 
```markdown
# Conflict Avoidance Patterns

Found 23 instances across 15 meetings where you used indirect 
communication or avoided addressing tensions directly.

## Pattern: Hedging on Critical Feedback

**Frequency**: 8 times across 7 meetings

**Example 1: 1:1 with Sarah** - 00:14:32

**What Happened**:
> "So, I was thinking... maybe we could, like, potentially 
> consider looking at the timeline again? I mean, if you 
> think that makes sense. But whatever you think is best!"

**Why This Matters**:
You needed to address that Sarah's project was behind schedule, 
but the hedging language ("maybe", "potentially", "if you think") 
and the deflection at the end ("whatever you think") made it easy 
for her to miss the urgency.

**Better Approach**:
"Sarah, the project is two weeks behind schedule. We need to 
discuss what's blocking progress and create a new timeline 
today."

[Additional examples...]

## Recommendations

1. **Name the issue directly** in the first sentence
2. **Remove hedging words** like "maybe," "kind of," "sort of"
3. **Ask specific questions** instead of hinting
4. **Schedule difficult conversations** instead of raising them casually
```

### 示例 2: 领导引导

**用户**: "Analyze my team meetings and tell me about my facilitation style." (分析我的团队会议并告诉我关于我的引导风格。)

**输出**: 提供关于以下的见解：
- 你与团队成员的说话比例 (60% vs. 40%)
- 你是提问还是陈述 (3:1 比例)
- 你如何处理分歧（倾向于过快解决）
- 谁说话最少以及你是否吸引他们参与
- 良好和错失的引导时刻的示例

### 示例 3: 个人发展跟踪

**用户**: "Compare my meetings from Q1 vs. Q2 to see if I've improved my listening skills." (比较我第一季度与第二季度的会议，看看我是否提高了倾听技能。)

**输出**: 创建一个比较分析，显示：
- 打断减少 (8 次/会议 → 3 次/会议)
- 澄清问题增加 (2 → 7 次/会议)
- 在他人想法基础上构建的改进
- 显示差异的具体示例
- 剩余的增长领域

## 设置提示

### 获取会议记录

**来自 Granola** (Lenny's newsletter 订阅免费)：
- Granola 自动转录你的会议
- 导出记录到文件夹：[如何操作的说明]
- 将 Claude Code 指向该文件夹

**来自 Zoom**：
- 启用带转录的云录制
- 会议后下载 VTT 或 SRT 文件
- 存储在专用文件夹中

**来自 Google Meet**：
- 使用 Google Docs 自动转录
- 将记录文档保存到文件夹
- 下载为 .txt 文件或给予 Claude Code 访问权限

**来自 Fireflies.ai, Otter.ai 等**：
- 批量导出记录
- 存储在本地文件夹中
- 对文件夹运行分析

### 最佳实践

1. **一致命名**：使用 `YYYY-MM-DD - Meeting Name.txt` 格式
2. **定期分析**：每月或每季度审查趋势
3. **具体查询**：一次询问一种行为以获得深度
4. **隐私**：将敏感会议数据保存在本地
5. **行动导向**：一次专注于一个改进领域

## 常见分析请求

- "When do I avoid difficult conversations?" (我何时避免困难的对话？)
- "How often do I interrupt others?" (我多久打断别人一次？)
- "What's my speaking vs. listening ratio?" (我的说话与倾听比例是多少？)
- "Do I ask good questions?" (我问的问题好吗？)
- "How do I handle disagreement?" (我如何处理分歧？)
- "Am I inclusive of all voices?" (我是否包容所有声音？)
- "Do I use too many filler words?" (我是否使用了太多填充词？)
- "How clear are my action items?" (我的行动项目有多清晰？)
- "Do I stay on agenda or get sidetracked?" (我是否保持在议程上还是跑题了？)
- "How has my communication changed over time?" (我的沟通随时间有何变化？)

## 相关用例

- 从见解中创建个人发展计划
- 准备带有示例的绩效评估材料
- 指导直接下属的沟通
- 分析销售或支持模式的客户电话
- 研究谈判策略和结果
