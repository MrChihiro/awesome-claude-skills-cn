---
name: content-research-writer
description: 通过进行研究、添加引用、改进吸引点、迭代大纲以及对每个部分提供实时反馈，协助编写高质量内容。将你的写作过程从单打独斗转变为合作伙伴关系。
---

# 内容研究作家 (Content Research Writer)

此技能充当你的写作伙伴，帮助你研究、列大纲、起草和改进内容，同时保持你独特的声音和风格。

## 何时使用此技能

- 编写博客文章、文章或时事通讯
- 创建教育内容或教程
- 起草思想领导力文章
- 研究和撰写案例研究
- 制作带有来源的技术文档
- 编写带有适当引用和参考文献的内容
- 改进吸引点和介绍
- 在写作时获得逐节反馈

## 此技能做什么

1. **协作大纲**：帮助你将想法构建成连贯的大纲
2. **研究协助**：查找相关信息并添加引用
3. **吸引点改进**：加强你的开场白以吸引注意力
4. **部分反馈**：在你写作时审查每个部分
5. **声音保留**：保持你的写作风格和语气
6. **引用管理**：正确添加和格式化参考文献
7. **迭代改进**：帮助你通过多次草稿进行改进

## 如何使用

### 设置你的写作环境

为你的文章创建一个专用文件夹：
```
mkdir ~/writing/my-article-title
cd ~/writing/my-article-title
```

创建你的草稿文件：
```
touch article-draft.md
```

从该目录打开 Claude Code 并开始写作。

### 基本工作流

1. **从大纲开始**：
```
Help me create an outline for an article about [topic]
(帮我创建一个关于 [主题] 的文章大纲)
```

2. **研究并添加引用**：
```
Research [specific topic] and add citations to my outline
(研究 [特定主题] 并将引用添加到我的大纲中)
```

3. **改进吸引点**：
```
Here's my introduction. Help me make the hook more compelling.
(这是我的介绍。帮我让吸引点更具吸引力。)
```

4. **获取部分反馈**：
```
I just finished the "Why This Matters" section. Review it and give feedback.
(我刚刚完成了“为什么这很重要”部分。审查它并给予反馈。)
```

5. **改进和润色**：
```
Review the full draft for flow, clarity, and consistency.
(审查完整草稿的流畅性、清晰度和一致性。)
```

## 指令

当用户请求写作帮助时：

1. **了解写作项目**
   
   提出澄清问题：
   - 主题和主要论点是什么？
   - 目标受众是谁？
   - 期望的长度/格式是什么？
   - 你的目标是什么？（教育、说服、娱乐、解释）
   - 有任何现有的研究或来源需要包含吗？
   - 你的写作风格是什么？（正式、对话式、技术性）

2. **协作大纲**
   
   帮助构建内容：
   
   ```markdown
   # Article Outline: [Title]
   
   ## Hook (吸引点)
   - [Opening line/story/statistic]
   - [Why reader should care]
   
   ## Introduction (介绍)
   - Context and background
   - Problem statement
   - What this article covers
   
   ## Main Sections (主要部分)
   
   ### Section 1: [Title]
   - Key point A
   - Key point B
   - Example/evidence
   - [Research needed: specific topic]
   
   ### Section 2: [Title]
   - Key point C
   - Key point D
   - Data/citation needed
   
   ### Section 3: [Title]
   - Key point E
   - Counter-arguments
   - Resolution
   
   ## Conclusion (结论)
   - Summary of main points
   - Call to action
   - Final thought
   
   ## Research To-Do (研究待办)
   - [ ] Find data on [topic]
   - [ ] Get examples of [concept]
   - [ ] Source citation for [claim]
   ```
   
   **迭代大纲**：
   - 根据反馈进行调整
   - 确保逻辑流畅
   - 识别研究差距
   - 标记需要深入研究的部分

3. **进行研究**
   
   当用户请求对某个主题进行研究时：
   
   - 搜索相关信息
   - 查找可信来源
   - 提取关键事实、引用和数据
   - 以请求的格式添加引用
   
   示例输出：
   ```markdown
   ## Research: AI Impact on Productivity
   
   Key Findings:
   
   1. **Productivity Gains**: Studies show 40% time savings for 
      content creation tasks [1]
   
   2. **Adoption Rates**: 67% of knowledge workers use AI tools 
      weekly [2]
   
   3. **Expert Quote**: "AI augments rather than replaces human 
      creativity" - Dr. Jane Smith, MIT [3]
   
   Citations:
   [1] McKinsey Global Institute. (2024). "The Economic Potential 
       of Generative AI"
   [2] Stack Overflow Developer Survey (2024)
   [3] Smith, J. (2024). MIT Technology Review interview
   
   Added to outline under Section 2.
   ```

4. **改进吸引点**
   
   当用户分享介绍时，分析并加强：
   
   **当前吸引点分析**：
   - 有效之处：[积极元素]
   - 可以更强之处：[改进领域]
   - 情感影响：[当前 vs. 潜在]
   
   **建议的替代方案**：
   
   选项 1：[大胆声明]
   > [示例]
   *为什么有效：[解释]*
   
   选项 2：[个人故事]
   > [示例]
   *为什么有效：[解释]*
   
   选项 3：[令人惊讶的数据]
   > [示例]
   *为什么有效：[解释]*
   
   **对吸引点的提问**：
   - 它是否引起好奇心？
   - 它是否承诺价值？
   - 它是否足够具体？
   - 它是否匹配受众？

5. **提供逐节反馈**
   
   当用户编写每个部分时，审查：
   
   ```markdown
   # Feedback: [Section Name]
   
   ## What Works Well ✓ (有效之处)
   - [Strength 1]
   - [Strength 2]
   - [Strength 3]
   
   ## Suggestions for Improvement (改进建议)
   
   ### Clarity (清晰度)
   - [Specific issue] → [Suggested fix]
   - [Complex sentence] → [Simpler alternative]
   
   ### Flow (流畅度)
   - [Transition issue] → [Better connection]
   - [Paragraph order] → [Suggested reordering]
   
   ### Evidence (证据)
   - [Claim needing support] → [Add citation or example]
   - [Generic statement] → [Make more specific]
   
   ### Style (风格)
   - [Tone inconsistency] → [Match your voice better]
   - [Word choice] → [Stronger alternative]
   
   ## Specific Line Edits (具体行编辑)
   
   Original:
   > [Exact quote from draft]
   
   Suggested:
   > [Improved version]
   
   Why: [Explanation]
   
   ## Questions to Consider (需要考虑的问题)
   - [Thought-provoking question 1]
   - [Thought-provoking question 2]
   
   Ready to move to next section!
   ```

6. **保留作者的声音**
   
   重要原则：
   
   - **学习他们的风格**：阅读现有的写作样本
   - **建议，不要替代**：提供选项，而不是指令
   - **匹配语气**：正式、随意、技术性、友好
   - **尊重选择**：如果他们更喜欢他们的版本，支持它
   - **增强，不要覆盖**：让他们的写作更好，而不是不同
   
   定期询问：
   - "这听起来像你吗？"
   - "这是正确的语气吗？"
   - "我应该更/更少 [正式/随意/技术性] 吗？"

7. **引用管理**
   
   根据用户偏好处理参考文献：
   
   **内联引用**：
   ```markdown
   Studies show 40% productivity improvement (McKinsey, 2024).
   ```
   
   **编号参考文献**：
   ```markdown
   Studies show 40% productivity improvement [1].
   
   [1] McKinsey Global Institute. (2024)...
   ```
   
   **脚注风格**：
   ```markdown
   Studies show 40% productivity improvement^1
   
   ^1: McKinsey Global Institute. (2024)...
   ```
   
   维护一个运行中的引用列表：
   ```markdown
   ## References
   
   1. Author. (Year). "Title". Publication.
   2. Author. (Year). "Title". Publication.
   ...
   ```

8. **最终审查和润色**
   
   当草稿完成时，提供全面的反馈：
   
   ```markdown
   # Full Draft Review
   
   ## Overall Assessment (总体评估)
   
   **Strengths**:
   - [Major strength 1]
   - [Major strength 2]
   - [Major strength 3]
   
   **Impact**: [Overall effectiveness assessment]
   
   ## Structure & Flow (结构与流畅度)
   - [Comments on organization]
   - [Transition quality]
   - [Pacing assessment]
   
   ## Content Quality (内容质量)
   - [Argument strength]
   - [Evidence sufficiency]
   - [Example effectiveness]
   
   ## Technical Quality (技术质量)
   - Grammar and mechanics: [assessment]
   - Consistency: [assessment]
   - Citations: [completeness check]
   
   ## Readability (可读性)
   - Clarity score: [evaluation]
   - Sentence variety: [evaluation]
   - Paragraph length: [evaluation]
   
   ## Final Polish Suggestions (最终润色建议)
   
   1. **Introduction**: [Specific improvements]
   2. **Body**: [Specific improvements]
   3. **Conclusion**: [Specific improvements]
   4. **Title**: [Options if needed]
   
   ## Pre-Publish Checklist (发布前清单)
   - [ ] All claims sourced
   - [ ] Citations formatted
   - [ ] Examples clear
   - [ ] Transitions smooth
   - [ ] Call to action present
   - [ ] Proofread for typos
   
   Ready to publish! 🚀
   ```

## 示例

### 示例 1: Teresa Torres 的工作流

**用户**: "I'm writing an article about continuous discovery. Help me create an outline." (我正在写一篇关于持续发现的文章。帮我创建一个大纲。)

**过程**:
1. 协作大纲结构
2. 识别研究需求
3. 用户开始写介绍
4. 审查并改进吸引点
5. 用户编写每个部分
6. 在每个部分后提供反馈
7. 进行研究并添加引用
8. 最终审查完整草稿
9. 润色并准备发布

**结果**: 一篇研究充分、引用恰当的文章，以 Teresa 的声音撰写，结构和流畅度强。

### 示例 2: 重研究文章

**用户**: "I'm writing about AI's impact on product management. Help me find current data and examples." (我正在写关于 AI 对产品管理影响的文章。帮我查找当前数据和示例。)

**输出**:
```markdown
## Research Compiled

### Recent Data
- Gartner: 80% of PMs will use AI tools by 2025 [1]
- Survey: 45% report faster feature shipping [2]
- Case study: Airbnb's AI-assisted prioritization [3]

### Expert Quotes
- "AI amplifies PM judgment, not replaces it" - Marty Cagan
- [Additional quotes with citations]

### Real Examples
1. **Company A**: Used AI for user research synthesis
   - Result: 60% time savings
   - Source: [citation]

2. **Company B**: AI-powered roadmap analysis
   - Result: Better stakeholder alignment
   - Source: [citation]

All added to your outline with proper citations.
```

### 示例 3: 吸引点改进

**用户的原始吸引点**:
> "Product management is changing because of AI. In this article, I'll discuss some ways AI affects product managers."
> (产品管理因 AI 而改变。在这篇文章中，我将讨论 AI 影响产品经理的一些方式。)

**改进选项**:

**选项 1 (数据驱动)**:
> "Last month, I asked AI to analyze 500 customer interviews. It took 30 minutes instead of 3 weeks. Product management will never be the same."
> (上个月，我让 AI 分析了 500 个客户访谈。它花了 30 分钟而不是 3 周。产品管理将不再一样。)

**选项 2 (提问)**:
> "What if you could talk to every customer, read every review, and analyze every support ticket—all before your morning coffee?"
> (如果你能在喝早咖啡之前与每位客户交谈、阅读每条评论并分析每张支持票，会怎样？)

**选项 3 (故事)**:
> "Sarah spent two weeks building the wrong feature. Not because she didn't understand her users, but because she couldn't process the hundreds of interviews fast enough to spot the pattern."
> (Sarah 花了两周时间构建了错误的功能。不是因为她不了解她的用户，而是因为她无法足够快地处理数百个访谈以发现模式。)

### 示例 4: 部分反馈

**用户**: "Just finished my 'Common Mistakes' section. Thoughts?" (刚刚完成了我的“常见错误”部分。想法？)

**响应**:
```markdown
# Feedback: Common Mistakes Section

## What Works Well ✓
- Strong examples (the Slack notification story)
- Clear structure (3 mistakes, clean layout)
- Practical advice for each mistake

## Suggestions

### Make It More Specific
Your second point says "Bad prioritization" but could be stronger:

Current:
> "Many teams prioritize badly by focusing on features instead of outcomes."

Suggested:
> "I've watched teams ship 14 features in a quarter yet move none of their key metrics. They prioritized activity over progress."

### Add Data
The third mistake would benefit from evidence:
> "[Add citation]: Studies show teams without regular user contact are 3x more likely to build unused features [needs source]"

### Flow Improvement
Consider reordering: Mistake 3 → Mistake 2 → Mistake 1
This builds from small to big impact.

Ready for the next section!
```

## 写作工作流

### 博客文章工作流
1. 一起列大纲
2. 研究关键点
3. 写介绍 → 获取反馈
4. 写正文部分 → 每个反馈
5. 写结论 → 最终审查
6. 润色和编辑

### 时事通讯工作流
1. 讨论吸引点想法
2. 快速大纲（较短格式）
3. 一次性起草
4. 审查清晰度和链接
5. 快速润色

### 技术教程工作流
1. 列出步骤大纲
2. 编写代码示例
3. 添加解释
4. 测试说明
5. 添加故障排除部分
6. 最终审查准确性

### 思想领导力工作流
1. 头脑风暴独特角度
2. 研究现有观点
3. 发展你的论点
4. 以强烈的 POV 写作
5. 添加支持证据
6. 制作引人注目的结论

## 专业提示

1. **在 VS Code 中工作**：对于长篇写作比 web Claude 更好
2. **一次一个部分**：逐步获取反馈
3. **单独保存研究**：保留一个 research.md 文件
4. **版本化你的草稿**：article-v1.md, article-v2.md 等
5. **朗读**：使用反馈来识别笨拙的句子
6. **设定截止日期**："我想今天完成草稿"
7. **休息**：写作，获取反馈，暂停，修改

## 文件组织

写作项目的推荐结构：

```
~/writing/article-name/
├── outline.md          # 你的大纲
├── research.md         # 所有研究和引用
├── draft-v1.md         # 初稿
├── draft-v2.md         # 修改稿
├── final.md            # 准备发布
├── feedback.md         # 收集的反馈
└── sources/            # 参考资料
    ├── study1.pdf
    └── article2.md
```

## 最佳实践

### 对于研究
- 引用前验证来源
- 尽可能使用最新数据
- 平衡不同观点
- 链接到原始来源

### 对于反馈
- 具体说明你想要的："这太技术性了吗？"
- 分享你的担忧："我担心这部分拖沓"
- 提问："这逻辑通顺吗？"
- 请求替代方案："解释这个的另一种方式是什么？"

### 对于声音
- 分享你的写作示例
- 指定语气偏好
- 指出好的匹配："这听起来像我！"
- 标记不匹配："对我的风格来说太正式了"

## 相关用例

- 从文章创建社交媒体帖子
- 为不同受众调整内容
- 编写电子邮件时事通讯
- 起草技术文档
- 创建演示内容
- 编写案例研究
- 开发课程大纲
