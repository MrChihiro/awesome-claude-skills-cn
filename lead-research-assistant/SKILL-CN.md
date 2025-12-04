---
name: lead-research-assistant
description: 通过分析你的业务、搜索目标公司并提供可操作的联系策略，为你的产品或服务识别高质量的潜在客户。非常适合销售、业务开发和营销专业人员。
---

# 潜在客户研究助手 (Lead Research Assistant)

此技能通过分析你的产品/服务、了解你的理想客户档案并提供可操作的外展策略，帮助你识别和限定业务的潜在客户。

## 何时使用此技能

- 为你的产品/服务寻找潜在客户或客户
- 建立要联系以建立合作伙伴关系的公司列表
- 识别用于销售外展的目标账户
- 研究符合你理想客户档案的公司
- 准备业务开发活动

## 此技能做什么

1. **了解你的业务**：分析你的产品/服务、价值主张和目标市场
2. **识别目标公司**：根据以下条件查找符合你理想客户档案的公司：
   - 行业和部门
   - 公司规模和位置
   - 技术栈和使用的工具
   - 增长阶段和融资
   - 你的产品解决的痛点
3. **优先排序潜在客户**：根据匹配得分和相关性对公司进行排名
4. **提供联系策略**：建议如何通过个性化消息接触每个潜在客户
5. **丰富数据**：收集有关决策者和公司背景的相关信息

## 如何使用

### 基本用法

只需描述你的产品/服务以及你在寻找什么：

```
I'm building [product description]. Find me 10 companies in [location/industry] 
that would be good leads for this.
(我正在构建 [产品描述]。为我找到 [位置/行业] 的 10 家公司，它们将是这方面的好潜在客户。)
```

### 与你的代码库一起使用

为了获得更好的结果，请从你的产品源代码目录运行此命令：

```
Look at what I'm building in this repository and identify the top 10 companies 
in [location/industry] that would benefit from this product.
(看看我在此存储库中构建的内容，并确定 [位置/行业] 中将从此产品中受益的前 10 家公司。)
```

### 高级用法

对于更有针对性的研究：

```
My product: [description]
Ideal customer profile:
- Industry: [industry]
- Company size: [size range]
- Location: [location]
- Current pain points: [pain points]
- Technologies they use: [tech stack]

Find me 20 qualified leads with contact strategies for each.
(我的产品：[描述]
理想客户档案：
- 行业：[行业]
- 公司规模：[规模范围]
- 位置：[位置]
- 当前痛点：[痛点]
- 他们使用的技术：[技术栈]

为我找到 20 个合格的潜在客户，并为每个提供联系策略。)
```

## 指令

当用户请求潜在客户研究时：

1. **了解产品/服务**
   - 如果在代码目录中，分析代码库以了解产品
   - 询问有关价值主张的澄清问题
   - 识别关键功能和优势
   - 了解它解决什么问题

2. **定义理想客户档案**
   - 确定目标行业和部门
   - 识别公司规模范围
   - 考虑地理偏好
   - 了解相关痛点
   - 注意任何技术要求

3. **研究和识别潜在客户**
   - 搜索符合标准的公司
   - 寻找需求的信号（招聘启事、技术栈、最近的新闻）
   - 考虑增长指标（融资、扩张、招聘）
   - 识别具有互补产品/服务的公司
   - 检查预算指标

4. **优先排序和评分**
   - 为每个潜在客户创建一个匹配得分 (1-10)
   - 考虑以下因素：
     - 与 ICP 的一致性
     - 迫切需求的信号
     - 预算可用性
     - 竞争格局
     - 时机指标

5. **提供可操作的输出**
   
   对于每个潜在客户，提供：
   - **公司名称**和网站
   - **为什么他们适合**：基于他们业务的具体原因
   - **优先级得分**：1-10 并附带解释
   - **决策者**：要针对的角色/头衔（例如，“工程副总裁”）
   - **联系策略**：个性化的方法建议
   - **价值主张**：你的产品如何解决他们的具体问题
   - **对话开场白**：外展中要提到的具体点
   - **LinkedIn URL**：如果可用，以便轻松连接

6. **格式化输出**

   以清晰、可扫描的格式呈现结果：

   ```markdown
   # Lead Research Results
   
   ## Summary
   - Total leads found: [X]
   - High priority (8-10): [X]
   - Medium priority (5-7): [X]
   - Average fit score: [X]
   
   ---
   
   ## Lead 1: [Company Name]
   
   **Website**: [URL]
   **Priority Score**: [X/10]
   **Industry**: [Industry]
   **Size**: [Employee count/revenue range]
   
   **Why They're a Good Fit**:
   [2-3 specific reasons based on their business]
   
   **Target Decision Maker**: [Role/Title]
   **LinkedIn**: [URL if available]
   
   **Value Proposition for Them**:
   [Specific benefit for this company]
   
   **Outreach Strategy**:
   [Personalized approach - mention specific pain points, recent company news, or relevant context]
   
   **Conversation Starters**:
   - [Specific point 1]
   - [Specific point 2]
   
   ---
   
   [Repeat for each lead]
   ```

7. **提供后续步骤**
   - 建议将结果保存到 CSV 以进行 CRM 导入
   - 提议起草个性化的外展消息
   - 建议根据时机进行优先排序
   - 建议对顶级潜在客户进行后续研究

## 示例

### 示例 1: 来自 Lenny's Newsletter

**用户**: "I'm building a tool that masks sensitive data in AI coding assistant queries. Find potential leads." (我正在构建一个在 AI 编码助手查询中屏蔽敏感数据的工具。寻找潜在客户。)

**输出**: 创建一个优先排序的公司列表，这些公司：
- 使用 AI 编码助手 (Copilot, Cursor 等)
- 处理敏感数据（金融科技、医疗保健、法律）
- 在其 GitHub 存储库中有使用编码代理的证据
- 可能在代码中意外暴露了敏感数据
- 包括相关决策者的 LinkedIn URL

### 示例 2: 本地业务

**用户**: "I run a consulting practice for remote team productivity. Find me 10 companies in the Bay Area that recently went remote." (我经营一家远程团队生产力咨询公司。为我找到湾区最近转向远程办公的 10 家公司。)

**输出**: 识别以下公司：
- 最近发布了远程招聘信息
- 宣布了远程优先政策
- 正在招聘分布式团队
- 显示出远程工作挑战的迹象
- 为每个公司提供个性化的外展策略

## 获得最佳结果的提示

- **具体说明**你的产品及其独特价值
- 如果适用，**从你的代码库运行**以获取自动上下文
- **提供上下文**关于你的理想客户档案
- **指定约束**如行业、位置或公司规模
- **请求后续**研究有前途的潜在客户以获得更深入的见解

## 相关用例

- 在识别潜在客户后起草个性化外展电子邮件
- 建立合格潜在客户的 CRM 就绪 CSV
- 详细研究特定公司
- 分析竞争对手的客户群
- 识别合作伙伴机会
