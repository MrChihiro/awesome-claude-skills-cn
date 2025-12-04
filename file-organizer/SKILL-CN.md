---
name: file-organizer
description: 通过理解上下文、查找重复项、建议更好的结构和自动执行清理任务，智能地组织计算机上的文件和文件夹。减少认知负担，无需手动操作即可保持数字工作区整洁。
---

# 文件组织器 (File Organizer)

此技能充当你的个人组织助手，帮助你在计算机上保持干净、合乎逻辑的文件结构，而无需持续手动组织的脑力开销。

## 何时使用此技能

- 你的下载文件夹一团糟
- 你找不到文件，因为它们到处都是
- 你有重复文件占用空间
- 你的文件夹结构不再合理
- 你想建立更好的组织习惯
- 你正在开始一个新项目并需要一个好的结构
- 你正在归档旧项目之前进行清理

## 此技能做什么

1. **分析当前结构**：审查你的文件夹和文件以了解你拥有什么
2. **查找重复项**：识别系统中的重复文件
3. **建议组织**：根据你的内容提出合乎逻辑的文件夹结构建议
4. **自动清理**：经你批准后移动、重命名和组织文件
5. **保持上下文**：根据文件类型、日期和内容做出明智的决定
6. **减少混乱**：识别你可能不再需要的旧文件

## 如何使用

### 从你的主目录

```
cd ~
```

然后运行 Claude Code 并寻求帮助：

```
Help me organize my Downloads folder
(帮我组织我的下载文件夹)
```

```
Find duplicate files in my Documents folder
(在我的文档文件夹中查找重复文件)
```

```
Review my project directories and suggest improvements
(审查我的项目目录并建议改进)
```

### 特定的组织任务

```
Organize these downloads into proper folders based on what they are
(根据这些下载的内容将它们组织到适当的文件夹中)
```

```
Find duplicate files and help me decide which to keep
(查找重复文件并帮我决定保留哪些)
```

```
Clean up old files I haven't touched in 6+ months
(清理我 6 个月以上未接触过的旧文件)
```

```
Create a better folder structure for my [work/projects/photos/etc]
(为我的 [工作/项目/照片/等] 创建更好的文件夹结构)
```

## 指令

当用户请求文件组织帮助时：

1. **了解范围**
   
   提出澄清问题：
   - 哪个目录需要组织？（下载、文档、整个主文件夹？）
   - 主要问题是什么？（找不到东西、重复项、太乱、没有结构？）
   - 有任何需要避免的文件或文件夹吗？（当前项目、敏感数据？）
   - 组织力度如何？（保守 vs. 全面清理）

2. **分析当前状态**
   
   审查目标目录：
   ```bash
   # Get overview of current structure
   ls -la [target_directory]
   
   # Check file types and sizes
   find [target_directory] -type f -exec file {} \; | head -20
   
   # Identify largest files
   du -sh [target_directory]/* | sort -rh | head -20
   
   # Count file types
   find [target_directory] -type f | sed 's/.*\.//' | sort | uniq -c | sort -rn
   ```
   
   总结发现：
   - 文件和文件夹总数
   - 文件类型细分
   - 大小分布
   - 日期范围
   - 明显的组织问题

3. **识别组织模式**
   
   根据文件，确定合乎逻辑的分组：
   
   **按类型**：
   - 文档 (PDFs, DOCX, TXT)
   - 图像 (JPG, PNG, SVG)
   - 视频 (MP4, MOV)
   - 归档 (ZIP, TAR, DMG)
   - 代码/项目 (包含代码的目录)
   - 电子表格 (XLSX, CSV)
   - 演示文稿 (PPTX, KEY)
   
   **按用途**：
   - 工作 vs. 个人
   - 活动 vs. 归档
   - 特定项目
   - 参考资料
   - 临时/草稿文件
   
   **按日期**：
   - 当前年/月
   - 往年
   - 非常旧（归档候选）

4. **查找重复项**
   
   当请求时，搜索重复项：
   ```bash
   # Find exact duplicates by hash
   find [directory] -type f -exec md5 {} \; | sort | uniq -d
   
   # Find files with same name
   find [directory] -type f -printf '%f\n' | sort | uniq -d
   
   # Find similar-sized files
   find [directory] -type f -printf '%s %p\n' | sort -n
   ```
   
   对于每组重复项：
   - 显示所有文件路径
   - 显示大小和修改日期
   - 推荐保留哪个（通常是最新的或命名最好的）
   - **重要**：在删除之前始终要求确认

5. **提出组织计划**
   
   在进行更改之前提出清晰的计划：
   
   ```markdown
   # Organization Plan for [Directory]
   
   ## Current State
   - X files across Y folders
   - [Size] total
   - File types: [breakdown]
   - Issues: [list problems]
   
   ## Proposed Structure
   
   ```
   [Directory]/
   ├── Work/
   │   ├── Projects/
   │   ├── Documents/
   │   └── Archive/
   ├── Personal/
   │   ├── Photos/
   │   ├── Documents/
   │   └── Media/
   └── Downloads/
       ├── To-Sort/
       └── Archive/
   ```
   
   ## Changes I'll Make
   
   1. **Create new folders**: [list]
   2. **Move files**:
      - X PDFs → Work/Documents/
      - Y images → Personal/Photos/
      - Z old files → Archive/
   3. **Rename files**: [any renaming patterns]
   4. **Delete**: [duplicates or trash files]
   
   ## Files Needing Your Decision
   
   - [List any files you're unsure about]
   
   Ready to proceed? (yes/no/modify)
   ```

6. **执行组织**
   
   批准后，系统地组织：
   
   ```bash
   # Create folder structure
   mkdir -p "path/to/new/folders"
   
   # Move files with clear logging
   mv "old/path/file.pdf" "new/path/file.pdf"
   
   # Rename files with consistent patterns
   # Example: "YYYY-MM-DD - Description.ext"
   ```
   
   **重要规则**：
   - 在删除任何内容之前始终确认
   - 记录所有移动以便可能撤消
   - 保留原始修改日期
   - 优雅地处理文件名冲突
   - 如果遇到意外情况，停止并询问

7. **提供摘要和维护提示**
   
   组织后：
   
   ```markdown
   # Organization Complete! ✨
   
   ## What Changed
   
   - Created [X] new folders
   - Organized [Y] files
   - Freed [Z] GB by removing duplicates
   - Archived [W] old files
   
   ## New Structure
   
   [Show the new folder tree]
   
   ## Maintenance Tips
   
   To keep this organized:
   
   1. **Weekly**: Sort new downloads
   2. **Monthly**: Review and archive completed projects
   3. **Quarterly**: Check for new duplicates
   4. **Yearly**: Archive old files
   
   ## Quick Commands for You
   
   ```bash
   # Find files modified this week
   find . -type f -mtime -7
   
   # Sort downloads by type
   [custom command for their setup]
   
   # Find duplicates
   [custom command]
   ```
   
   Want to organize another folder?
   ```

## 示例

### 示例 1: 组织下载 (来自 Justin Dielmann)

**用户**: "My Downloads folder is a mess with 500+ files. Help me organize it." (我的下载文件夹一团糟，有 500 多个文件。帮我组织它。)

**过程**:
1. 分析下载文件夹
2. 发现模式：工作文档、个人照片、安装程序、随机 PDF
3. 提出结构：
   - Downloads/
     - Work/
     - Personal/
     - Installers/ (DMG, PKG 文件)
     - Archive/
     - ToSort/ (需要决定的东西)
4. 请求确认
5. 根据内容和名称智能移动文件
6. 结果：500 个文件 → 5 个有组织的文件夹

### 示例 2: 查找并删除重复项

**用户**: "Find duplicate files in my Documents and help me decide which to keep." (在我的文档中查找重复文件并帮我决定保留哪些。)

**输出**:
```markdown
# Found 23 Sets of Duplicates (156 MB total)

## Duplicate Set 1: "proposal.pdf"
- `/Documents/proposal.pdf` (2.3 MB, modified: 2024-03-15)
- `/Documents/old/proposal.pdf` (2.3 MB, modified: 2024-03-15)
- `/Desktop/proposal.pdf` (2.3 MB, modified: 2024-03-10)

**Recommendation**: Keep `/Documents/proposal.pdf` (most recent in correct location)
Delete the other 2 copies?

[Continue for all duplicates...]
```

### 示例 3: 重组项目文件夹

**用户**: "Review my ~/Projects directory and suggest improvements." (审查我的 ~/Projects 目录并建议改进。)

**输出**:
```markdown
# Analysis of ~/Projects

## Current Structure Issues
- Mix of active and archived projects (3+ years old)
- No consistent naming convention
- Some projects at root, others in random subfolders
- Duplicate folders (project-name, project-name-old, project-name-v2)

## Proposed Structure

```
Projects/
├── Active/
│   ├── client-work/
│   ├── side-projects/
│   └── learning/
├── Archive/
│   ├── 2022/
│   ├── 2023/
│   └── 2024/
└── Templates/
```

## Specific Changes
1. Move 12 projects not touched since 2022 → Archive/
2. Consolidate 4 duplicate project folders
3. Rename projects to consistent format: "client-name-project-name"
4. Create Archive for old work

Want me to implement this?
```

### 示例 4: 按日期组织照片

**用户**: "Organize my photo folders by year and month." (按年和月组织我的照片文件夹。)

**输出**: 创建如下结构：
```
Photos/
├── 2023/
│   ├── 01-January/
│   ├── 02-February/
│   └── ...
├── 2024/
│   ├── 01-January/
│   └── ...
└── Unsorted/
```

然后根据 EXIF 数据或文件修改日期移动照片。

## 常见组织任务

### 下载清理
```
Organize my Downloads folder - move documents to Documents, 
images to Pictures, keep installers separate, and archive files 
older than 3 months.
(组织我的下载文件夹 - 将文档移动到文档，图像移动到图片，保持安装程序分开，并归档超过 3 个月的文件。)
```

### 项目组织
```
Review my Projects folder structure and help me separate active 
projects from old ones I should archive.
(审查我的项目文件夹结构并帮我将活动项目与我应该归档的旧项目分开。)
```

### 重复项删除
```
Find all duplicate files in my Documents folder and help me 
decide which ones to keep.
(查找我的文档文件夹中的所有重复文件并帮我决定保留哪些。)
```

### 桌面清理
```
My Desktop is covered in files. Help me organize everything into 
my Documents folder properly.
(我的桌面上满是文件。帮我将所有内容正确组织到我的文档文件夹中。)
```

### 照片组织
```
Organize all photos in this folder by date (year/month) based 
on when they were taken.
(根据拍摄时间按日期（年/月）组织此文件夹中的所有照片。)
```

### 工作/个人分离
```
Help me separate my work files from personal files across my 
Documents folder.
(帮我将我的工作文件与我的文档文件夹中的个人文件分开。)
```

## 专业提示

1. **从小处着手**：从一个凌乱的文件夹（如下载）开始以建立信任
2. **定期维护**：每周对下载进行清理
3. **一致命名**：对重要文件使用 "YYYY-MM-DD - Description" 格式
4. **积极归档**：将旧项目移动到归档而不是删除
5. **保持活动分离**：在活动工作和归档工作之间保持清晰的界限
6. **相信过程**：让 Claude 处理东西去哪里的认知负担

## 最佳实践

### 文件夹命名
- 使用清晰、描述性的名称
- 避免空格（使用连字符或下划线）
- 具体："client-proposals" 而不是 "docs"
- 使用前缀进行排序："01-current", "02-archive"

### 文件命名
- 包括日期："2024-10-17-meeting-notes.md"
- 描述性："q3-financial-report.xlsx"
- 避免名称中的版本号（改用版本控制）
- 删除下载伪影："document-final-v2 (1).pdf" → "document.pdf"

### 何时归档
- 6 个月以上未接触的项目
- 以后可能引用的已完成工作
- 迁移到新系统后的旧版本
- 你犹豫要不要删除的文件（先归档）

## 相关用例

- 为新计算机设置组织
- 准备文件进行备份/归档
- 在存储清理之前进行清理
- 组织共享团队文件夹
- 构建新项目目录
