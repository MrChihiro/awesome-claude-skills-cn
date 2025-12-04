---
name: raffle-winner-picker
description: 从列表、电子表格或 Google 表格中随机挑选赠品、抽奖和竞赛的获胜者。确保公平、无偏见的透明选择。
---

# 抽奖获胜者选择器 (Raffle Winner Picker)

此技能从列表、电子表格或 Google 表格中随机选择赠品和竞赛的获胜者。

## 何时使用此技能

- 运行社交媒体赠品活动
- 在活动中挑选抽奖获胜者
- 随机选择调查或测试的参与者
- 从竞赛提交中选择获胜者
- 公平分配有限的名额或资源
- 随机团队分配

## 此技能做什么

1. **随机选择**：使用加密随机选择
2. **多来源**：适用于 CSV、Excel、Google 表格或普通列表
3. **多位获胜者**：可以挑选一位或多位获胜者
4. **防止重复**：确保同一个人不能赢两次
5. **透明结果**：清晰显示选择过程
6. **获胜者详情**：显示有关获胜者的所有相关信息

## 如何使用

### 从 Google 表格

```
Pick a random row from this Google Sheet to select a winner 
for a giveaway: [Sheet URL]
(从此 Google 表格中随机挑选一行以选择赠品获胜者：[表格 URL])
```

### 从本地文件

```
Pick 3 random winners from entries.csv
(从 entries.csv 中挑选 3 位随机获胜者)
```

### 从列表

```
Pick a random winner from this list:
- Alice (alice@email.com)
- Bob (bob@email.com)
- Carol (carol@email.com)
...
(从此列表中挑选一位随机获胜者：...)
```

### 多位获胜者

```
Pick 5 random winners from contest-entries.xlsx, 
make sure no duplicates
(从 contest-entries.xlsx 中挑选 5 位随机获胜者，确保没有重复)
```

## 示例

**用户**: "Pick a random row from this Google Sheet to select a winner for a giveaway." (从此 Google 表格中随机挑选一行以选择赠品获胜者。)

**输出**:
```
Accessing Google Sheet...
Total entries found: 247

Randomly selecting winner...

🎉 WINNER SELECTED! 🎉

Row #142
Name: Sarah Johnson
Email: sarah.j@email.com
Entry Date: March 10, 2024
Comment: "Love your newsletter!"

Selection method: Cryptographically random
Timestamp: 2024-03-15 14:32:18 UTC

Would you like to:
- Pick another winner (excluding Sarah)?
- Export winner details?
- Pick runner-ups?
```

**灵感来源：** Lenny 的用例 - 从他的订阅者 Slack 社区中挑选 Sora 2 赠品获胜者

## 功能

### 公平选择
- 使用安全随机数生成
- 无偏见或模式
- 透明过程
- 可重复的种子（用于验证）

### 排除
```
Pick a random winner excluding previous winners: 
Alice, Bob, Carol
(挑选一位随机获胜者，排除以前的获胜者：Alice, Bob, Carol)
```

### 加权选择
```
Pick a winner with weighted probability based on 
the "entries" column (1 entry = 1 ticket)
(根据 "entries" 列（1 个条目 = 1 张票）以加权概率挑选获胜者)
```

### 亚军
```
Pick 1 winner and 3 runner-ups from the list
(从列表中挑选 1 位获胜者和 3 位亚军)
```

## 示例工作流

### 社交媒体赠品
1. 从 Google 表单导出条目到表格
2. "Pick a random winner from [Sheet URL]"
3. 验证获胜者详情
4. 公开宣布并附带时间戳

### 活动抽奖
1. 创建参与者姓名和电子邮件的 CSV
2. "Pick 10 random winners from attendees.csv"
3. 导出获胜者列表
4. 直接给获胜者发电子邮件

### 团队分配
1. 拥有参与者列表
2. "Randomly split this list into 4 equal teams" (将此列表随机分成 4 个相等的团队)
3. 审查分配
4. 分享团队名单

## 提示

- **记录过程**：保存时间戳和方法
- **公开宣布**：分享选择细节以保持透明度
- **检查资格**：验证获胜者是否符合竞赛规则
- **拥有备份**：挑选亚军以防获胜者不合格
- **导出结果**：保存获胜者列表以作记录

## 隐私与公平

✓ 使用加密安全随机性
✓ 不可能操纵
✓ 记录时间戳以供验证
✓ 可以提供种子用于第三方验证
✓ 尊重数据隐私

## 常见用例

- 时事通讯订阅者赠品
- 产品发布抽奖
- 会议门票抽奖
- Beta 测试人员选择
- 焦点小组参与者选择
- 活动中的随机奖品分发
