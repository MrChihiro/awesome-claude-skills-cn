---
name: competitive-ads-extractor
description: 从广告库（Facebook, LinkedIn 等）中提取并分析竞争对手的广告，以了解哪些信息、问题和创意方法正在发挥作用。帮助启发和改进你自己的广告活动。
---

# 竞品广告提取器 (Competitive Ads Extractor)

此技能从广告库中提取竞争对手的广告，并分析哪些是有效的——他们强调的问题、他们针对的用例以及产生共鸣的文案/创意。

## 何时使用此技能

- 研究竞争对手的广告策略
- 为你自己的广告寻找灵感
- 了解市场定位
- 识别成功的广告模式
- 分析有效的信息
- 发现新的用例或痛点
- 用经过验证的概念规划广告活动

## 此技能做什么

1. **提取广告**：从 Facebook 广告库、LinkedIn 等抓取广告
2. **捕获截图**：保存所有广告的视觉副本
3. **分析信息**：识别问题、用例和价值主张
4. **分类广告**：按主题、受众或格式分组
5. **识别模式**：发现常见的成功方法
6. **提供见解**：解释为什么某些广告可能表现良好

## 如何使用

### 基本提取

```
Extract all current ads from [Competitor Name] on Facebook Ad Library
(从 Facebook 广告库中提取 [竞争对手名称] 的所有当前广告)
```

```
Scrape ads from [Company] and analyze their messaging
(从 [公司] 抓取广告并分析他们的信息)
```

### 特定分析

```
Get all ads from [Competitor] focusing on their messaging 
about [specific problem]. What pain points are they highlighting?
(获取 [竞争对手] 关于 [特定问题] 的信息的所有广告。他们强调了哪些痛点？)
```

### 竞争对手集

```
Extract ads from these 5 competitors: [list]. 
Compare their approaches and tell me what's working.
(提取这 5 个竞争对手的广告：[列表]。比较他们的方法并告诉我什么有效。)
```

### 特定平台

```
Get LinkedIn ads from [Competitor] and analyze their 
B2B positioning strategy
(从 [竞争对手] 获取 LinkedIn 广告并分析他们的 B2B 定位策略)
```

## 示例

**用户**: "Extract ads from Notion on Facebook Ad Library and tell me what messaging is working for them." (从 Facebook 广告库中提取 Notion 的广告，并告诉我什么信息对他们有效。)

**过程**:
```
Accessing Facebook Ad Library...
Searching for: Notion
Found: 23 active ads

Extracting screenshots...
[████████████████████] 100%

Saved to: competitor-ads/notion/
- ad-001-collaboration.png
- ad-002-productivity.png
- ad-003-templates.png
...

Analyzing messaging...
```

**输出**:
```
# Notion Ad Analysis

## Overview
- Total Ads: 23 active
- Primary Themes: Productivity (35%), Collaboration (30%), 
  Templates (20%), AI Features (15%)
- Ad Formats: Static images (60%), Video (40%)
- CTA Patterns: "Try for free", "Get started"

## Key Problems They're Highlighting

1. **Scattered Information** (8 ads)
   Copy: "Stop switching between 10 different tools"
   Why it works: Direct pain point many teams face

2. **Meeting Overload** (5 ads)
   Copy: "Replace unnecessary meetings with async updates"
   Why it works: Post-COVID remote work pain point

3. **Lost Documentation** (4 ads)
   Copy: "Never ask 'where is that doc?' again"
   Why it works: Universal workplace frustration

## Successful Creative Patterns

### Pattern 1: Before/After Split
- Shows chaotic tool landscape → Clean Notion workspace
- Used in 6 high-performing ads
- Visual metaphor is immediately clear

### Pattern 2: Feature Showcase
- GIF of actual product usage
- Shows specific feature in 5 seconds
- Used for new features (AI, templates)

### Pattern 3: Social Proof
- "Join 20M users" messaging
- Customer logos
- Used in 4 ads targeting enterprise

## Copy That's Working

Best Headlines:
1. "Your team's knowledge, finally in one place"
   → Benefit-focused, addresses pain directly
   
2. "The all-in-one workspace"
   → Clear positioning, broad appeal
   
3. "AI that actually helps you work"
   → Addresses AI skepticism, practical angle

Best Body Copy Patterns:
- Short sentences (under 10 words)
- Focus on outcomes not features
- Include specific numbers ("Cut meetings by 50%")

## Audience Targeting Insights

Based on ad variations:
- Startup founders: Solo productivity angle
- Team leads: Collaboration and alignment
- Enterprise: Security and compliance mentions
- Students: Free plan, templates, organization

## Recommendations for Your Ads

1. **Test the "tool sprawl" pain point**
   → Strong resonance based on their ad frequency

2. **Use product screenshots over abstract visuals**
   → All their top ads show actual UI

3. **Lead with the problem, not the solution**
   → "Tired of X?" performs better than "Introducing Y"

4. **Keep copy under 100 characters**
   → Their shortest ads seem most frequent

5. **Test before/after visual formats**
   → Proven pattern in their creative

## Files Saved
- All ads: ~/competitor-ads/notion/
- Analysis: ~/competitor-ads/notion/analysis.md
- Best performers: ~/competitor-ads/notion/top-10/
```

**灵感来源:** Lenny's Newsletter 中 Sumant Subrahmanya 的用例

## 你可以学到什么

### 信息分析
- 他们强调什么问题
- 他们如何针对竞争对手进行定位
- 产生共鸣的价值主张
- 目标受众细分

### 创意模式
- 有效的视觉风格
- 视频 vs 静态图像表现
- 配色方案和品牌推广
- 布局模式

### 文案公式
- 标题结构
- 号召性用语模式
- 长度和语气
- 情感触发点

### 活动策略
- 季节性活动
- 产品发布方法
- 功能公告策略
- 重定向模式

## 最佳实践

### 法律与道德
✓ 仅用于研究和灵感
✓ 不要直接复制广告
✓ 尊重知识产权
✓ 使用见解来指导原创创意
✗ 不要剽窃文案或窃取设计

### 分析提示
1. **寻找模式**：什么主题重复出现？
2. **随时间跟踪**：每月保存广告以查看演变
3. **测试假设**：为你的品牌调整成功的模式
4. **按受众细分**：针对不同目标的不同信息
5. **比较平台**：LinkedIn 与 Facebook 的信息不同

## 高级功能

### 趋势跟踪
```
Compare [Competitor]'s ads from Q1 vs Q2. 
What messaging has changed?
(比较 [竞争对手] Q1 与 Q2 的广告。什么信息发生了变化？)
```

### 多竞争对手分析
```
Extract ads from [Company A], [Company B], [Company C]. 
What are the common patterns? Where do they differ?
(提取 [公司 A]、[公司 B]、[公司 C] 的广告。常见的模式是什么？它们在哪里不同？)
```

### 行业基准
```
Show me ad patterns across the top 10 project management 
tools. What problems do they all focus on?
(向我展示前 10 名项目管理工具的广告模式。他们都关注什么问题？)
```

### 格式分析
```
Analyze video ads vs static image ads from [Competitor]. 
Which gets more engagement? (if data available)
(分析 [竞争对手] 的视频广告与静态图像广告。哪个获得更多参与？（如果数据可用）)
```

## 常见工作流

### 广告活动规划
1. 提取竞争对手广告
2. 识别成功模式
3. 注意他们信息中的差距
4. 头脑风暴独特的角度
5. 起草测试广告变体

### 定位研究
1. 获取 5 个竞争对手的广告
2. 绘制他们的定位图
3. 寻找服务不足的角度
4. 开发差异化信息
5. 针对他们的方法进行测试

### 创意灵感
1. 按主题提取广告
2. 分析视觉模式
3. 注意颜色和布局趋势
4. 调整成功模式
5. 创建原创变体

## 成功提示

1. **定期监控**：每月检查变化
2. **广泛研究**：也要关注相邻的竞争对手
3. **保存一切**：建立参考库
4. **测试见解**：运行你自己的实验
5. **跟踪表现**：A/B 测试受启发的概念
6. **保持原创**：用于灵感，而非复制
7. **多平台**：比较 Facebook, LinkedIn, TikTok 等

## 输出格式

- **截图**：所有广告保存为图像
- **分析报告**：见解的 Markdown 摘要
- **电子表格**：包含广告文案、CTA、主题的 CSV
- **演示文稿**：表现最佳者的视觉幻灯片
- **模式库**：按方法分类

## 相关用例

- 为你的活动编写更好的广告文案
- 了解市场定位
- 发现你信息中的内容差距
- 发现你产品的新用例
- 规划产品营销策略
- 启发社交媒体内容
