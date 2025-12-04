---
name: invoice-organizer
description: 通过读取杂乱的文件、提取关键信息、一致地重命名并将它们分类到逻辑文件夹中，自动组织发票和收据以进行税务准备。将数小时的手动记账转变为几分钟的自动组织。
---

# 发票组织器 (Invoice Organizer)

此技能将混乱的发票、收据和财务文件文件夹转换为干净、可用于税务的归档系统，无需手动操作。

## 何时使用此技能

- 准备税务季节并需要有组织的记录
- 管理多个供应商的业务支出
- 整理杂乱文件夹或电子邮件下载中的收据
- 为持续的记账设置自动发票归档
- 按年份或类别归档财务记录
- 核对费用以进行报销
- 为会计师准备文件

## 此技能做什么

1. **读取发票内容**：从 PDF、图像和文档中提取信息：
   - 供应商/公司名称
   - 发票号码
   - 日期
   - 金额
   - 产品或服务描述
   - 付款方式

2. **一致地重命名文件**：创建标准化的文件名：
   - 格式：`YYYY-MM-DD Vendor - Invoice - ProductOrService.pdf`
   - 示例：`2024-03-15 Adobe - Invoice - Creative Cloud.pdf`

3. **按类别组织**：分类到逻辑文件夹中：
   - 按供应商
   - 按支出类别（软件、办公、旅行等）
   - 按时间段（年、季度、月）
   - 按税务类别（可扣除、个人等）

4. **处理多种格式**：适用于：
   - PDF 发票
   - 扫描的收据 (JPG, PNG)
   - 电子邮件附件
   - 屏幕截图
   - 银行对账单

5. **保留原件**：在组织副本的同时保留原始文件

## 如何使用

### 基本用法

导航到你杂乱的发票文件夹：
```
cd ~/Desktop/receipts-to-sort
```

然后询问 Claude Code：
```
Organize these invoices for taxes
(为税务组织这些发票)
```

或者更具体地：
```
Read all invoices in this folder, rename them to 
"YYYY-MM-DD Vendor - Invoice - Product.pdf" format, 
and organize them by vendor
(读取此文件夹中的所有发票，将它们重命名为 "YYYY-MM-DD Vendor - Invoice - Product.pdf" 格式，并按供应商组织它们)
```

### 高级组织

```
Organize these invoices:
1. Extract date, vendor, and description from each file
2. Rename to standard format
3. Sort into folders by expense category (Software, Office, Travel, etc.)
4. Create a CSV spreadsheet with all invoice details for my accountant
(组织这些发票：
1. 从每个文件中提取日期、供应商和描述
2. 重命名为标准格式
3. 按支出类别（软件、办公、旅行等）分类到文件夹中
4. 为我的会计师创建一个包含所有发票详细信息的 CSV 电子表格)
```

## 指令

当用户请求发票组织时：

1. **扫描文件夹**
   
   识别所有发票文件：
   ```bash
   # Find all invoice-related files
   find . -type f \( -name "*.pdf" -o -name "*.jpg" -o -name "*.png" \) -print
   ```
   
   报告发现：
   - 文件总数
   - 文件类型
   - 日期范围（如果可以从名称中辨别）
   - 当前组织（或缺乏组织）

2. **从每个文件中提取信息**
   
   对于每个发票，提取：
   
   **从 PDF 发票**：
   - 使用文本提取读取发票内容
   - 寻找常见模式：
     - "Invoice Date:", "Date:", "Issued:"
     - "Invoice #:", "Invoice Number:"
     - 公司名称（通常在顶部）
     - "Amount Due:", "Total:", "Amount:"
     - "Description:", "Service:", "Product:"
   
   **从图像收据**：
   - 从图像中读取可见文本
   - 识别供应商名称（通常在顶部）
   - 寻找日期（常见格式）
   - 找到总金额
   
   **对于不清晰文件的回退**：
   - 使用文件名线索
   - 检查文件创建/修改日期
   - 如果关键信息缺失，标记为手动审查

3. **确定组织策略**
   
   如果未指定，询问用户偏好：
   
   ```markdown
   I found [X] invoices from [date range].
   
   How would you like them organized?
   
   1. **By Vendor** (Adobe/, Amazon/, Stripe/, etc.)
   2. **By Category** (Software/, Office Supplies/, Travel/, etc.)
   3. **By Date** (2024/Q1/, 2024/Q2/, etc.)
   4. **By Tax Category** (Deductible/, Personal/, etc.)
   5. **Custom** (describe your structure)
   
   Or I can use a default structure: Year/Category/Vendor
   ```

4. **创建标准化文件名**
   
   对于每个发票，按照此模式创建文件名：
   
   ```
   YYYY-MM-DD Vendor - Invoice - Description.ext
   ```
   
   示例：
   - `2024-03-15 Adobe - Invoice - Creative Cloud.pdf`
   - `2024-01-10 Amazon - Receipt - Office Supplies.pdf`
   - `2023-12-01 Stripe - Invoice - Monthly Payment Processing.pdf`
   
   **文件名最佳实践**：
   - 删除除连字符以外的特殊字符
   - 正确大写供应商名称
   - 保持描述简洁但有意义
   - 使用一致的日期格式 (YYYY-MM-DD) 进行排序
   - 保留原始文件扩展名

5. **执行组织**
   
   在移动文件之前，展示计划：
   
   ```markdown
   # Organization Plan
   
   ## Proposed Structure
   ```
   Invoices/
   ├── 2023/
   │   ├── Software/
   │   │   ├── Adobe/
   │   │   └── Microsoft/
   │   ├── Services/
   │   └── Office/
   └── 2024/
       ├── Software/
       ├── Services/
       └── Office/
   ```
   
   ## Sample Changes
   
   Before: `invoice_adobe_march.pdf`
   After: `2024-03-15 Adobe - Invoice - Creative Cloud.pdf`
   Location: `Invoices/2024/Software/Adobe/`
   
   Before: `IMG_2847.jpg`
   After: `2024-02-10 Staples - Receipt - Office Supplies.jpg`
   Location: `Invoices/2024/Office/Staples/`
   
   Process [X] files? (yes/no)
   ```
   
   批准后：
   ```bash
   # Create folder structure
   mkdir -p "Invoices/2024/Software/Adobe"
   
   # Copy (don't move) to preserve originals
   cp "original.pdf" "Invoices/2024/Software/Adobe/2024-03-15 Adobe - Invoice - Creative Cloud.pdf"
   
   # Or move if user prefers
   mv "original.pdf" "new/path/standardized-name.pdf"
   ```

6. **生成摘要报告**
   
   创建一个包含所有发票详细信息的 CSV 文件：
   
   ```csv
   Date,Vendor,Invoice Number,Description,Amount,Category,File Path
   2024-03-15,Adobe,INV-12345,Creative Cloud,52.99,Software,Invoices/2024/Software/Adobe/2024-03-15 Adobe - Invoice - Creative Cloud.pdf
   2024-03-10,Amazon,123-4567890-1234567,Office Supplies,127.45,Office,Invoices/2024/Office/Amazon/2024-03-10 Amazon - Receipt - Office Supplies.pdf
   ...
   ```
   
   此 CSV 用于：
   - 导入会计软件
   - 与会计师分享
   - 费用跟踪和报告
   - 税务准备

7. **提供完成摘要**
   
   ```markdown
   # Organization Complete! 📊
   
   ## Summary
   - **Processed**: [X] invoices
   - **Date range**: [earliest] to [latest]
   - **Total amount**: $[sum] (if amounts extracted)
   - **Vendors**: [Y] unique vendors
   
   ## New Structure
   ```
   Invoices/
   ├── 2024/ (45 files)
   │   ├── Software/ (23 files)
   │   ├── Services/ (12 files)
   │   └── Office/ (10 files)
   └── 2023/ (12 files)
   ```
   
   ## Files Created
   - `/Invoices/` - Organized invoices
   - `/Invoices/invoice-summary.csv` - Spreadsheet for accounting
   - `/Invoices/originals/` - Original files (if copied)
   
   ## Files Needing Review
   [List any files where information couldn't be extracted completely]
   
   ## Next Steps
   1. Review the `invoice-summary.csv` file
   2. Check files in "Needs Review" folder
   3. Import CSV into your accounting software
   4. Set up auto-organization for future invoices
   
   Ready for tax season! 🎉
   ```

## 示例

### 示例 1: 税务准备 (来自 Martin Merschroth)

**用户**: "I have a messy folder of invoices for taxes. Sort them and rename properly." (我有一个杂乱的发票文件夹用于税务。对它们进行分类并正确重命名。)

**过程**:
1. 扫描文件夹：发现 147 个 PDF 和图像
2. 读取每个发票以提取：
   - 日期
   - 供应商名称
   - 发票号码
   - 产品/服务描述
3. 重命名所有文件：`YYYY-MM-DD Vendor - Invoice - Product.pdf`
4. 组织到：`2024/Software/`, `2024/Travel/` 等
5. 为会计师创建 `invoice-summary.csv`
6. 结果：几分钟内完成税务准备好的有组织发票

### 示例 2: 每月费用核对

**用户**: "Organize my business receipts from last month by category." (按类别组织我上个月的业务收据。)

**输出**:
```markdown
# March 2024 Receipts Organized

## By Category
- Software & Tools: $847.32 (12 invoices)
- Office Supplies: $234.18 (8 receipts)
- Travel & Meals: $1,456.90 (15 receipts)
- Professional Services: $2,500.00 (3 invoices)

Total: $5,038.40

All receipts renamed and filed in:
`Business-Receipts/2024/03-March/[Category]/`

CSV export: `march-2024-expenses.csv`
```

### 示例 3: 多年归档

**用户**: "I have 3 years of random invoices. Organize them by year, then by vendor." (我有 3 年的随机发票。按年份组织它们，然后按供应商。)

**输出**: 创建结构：
```
Invoices/
├── 2022/
│   ├── Adobe/
│   ├── Amazon/
│   └── ...
├── 2023/
│   ├── Adobe/
│   ├── Amazon/
│   └── ...
├── 2024/
│   ├── Adobe/
│   ├── Amazon/
│   └── ...
```

每个文件都已正确重命名，包含日期和描述。

### 示例 4: 电子邮件下载清理

**用户**: "I download invoices from Gmail. They're all named 'invoice.pdf', 'invoice(1).pdf', etc. Fix this mess." (我从 Gmail 下载发票。它们都命名为 'invoice.pdf', 'invoice(1).pdf' 等。解决这个混乱。)

**输出**:
```markdown
Found 89 files all named "invoice*.pdf"

Reading each file to extract real information...

Renamed examples:
- invoice.pdf → 2024-03-15 Shopify - Invoice - Monthly Subscription.pdf
- invoice(1).pdf → 2024-03-14 Google - Invoice - Workspace.pdf
- invoice(2).pdf → 2024-03-10 Netlify - Invoice - Pro Plan.pdf

All files renamed and organized by vendor.
```

## 常见组织模式

### 按供应商（简单）
```
Invoices/
├── Adobe/
├── Amazon/
├── Google/
└── Microsoft/
```

### 按年份和类别（税务友好）
```
Invoices/
├── 2023/
│   ├── Software/
│   ├── Hardware/
│   ├── Services/
│   └── Travel/
└── 2024/
    └── ...
```

### 按季度（详细跟踪）
```
Invoices/
├── 2024/
│   ├── Q1/
│   │   ├── Software/
│   │   ├── Office/
│   │   └── Travel/
│   └── Q2/
│       └── ...
```

### 按税务类别（会计师就绪）
```
Invoices/
├── Deductible/
│   ├── Software/
│   ├── Office/
│   └── Professional-Services/
├── Partially-Deductible/
│   └── Meals-Travel/
└── Personal/
```

## 自动化设置

对于持续组织：

```
Create a script that watches my ~/Downloads/invoices folder 
and auto-organizes any new invoice files using our standard 
naming and folder structure.
(创建一个脚本来监视我的 ~/Downloads/invoices 文件夹，并使用我们的标准命名和文件夹结构自动组织任何新的发票文件。)
```

这创建了一个持久的解决方案，在发票到达时组织它们。

## 专业提示

1. **扫描电子邮件为 PDF**：使用预览或类似工具首先将电子邮件发票保存为 PDF
2. **一致下载**：将所有发票保存到一个文件夹以进行批量处理
3. **每月例行程序**：每月组织发票，而不是每年
4. **备份原件**：在重组之前保留原始文件
5. **在 CSV 中包含金额**：用于预算跟踪
6. **按可扣除性标记**：注明哪些费用是可免税的
7. **保留收据 7 年**：标准审计期

## 处理特殊情况

### 缺失信息
如果无法提取日期/供应商：
- 标记文件以进行手动审查
- 使用文件修改日期作为回退
- 创建 "Needs-Review/" 文件夹

### 重复发票
如果同一发票出现多次：
- 比较文件哈希
- 保留最高质量版本
- 在摘要中注明重复项

### 多页发票
对于拆分在文件中的发票：
- 如果需要，合并 PDF
- 对部分使用一致的命名
- 在 CSV 中注明发票是否拆分

### 非标准格式
对于不寻常的收据格式：
- 提取可能的内容
- 标准化你能做的
- 如果关键信息缺失，标记为审查

## 相关用例

- 创建费用报告以进行报销
- 组织银行对账单
- 管理供应商合同
- 归档旧财务记录
- 准备审计
- 跟踪随时间变化的订阅成本
