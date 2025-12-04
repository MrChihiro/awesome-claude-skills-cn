---
name: artifacts-builder
description: 一套使用现代前端 Web 技术（React, Tailwind CSS, shadcn/ui）创建精细、多组件 claude.ai HTML artifacts 的工具。适用于需要状态管理、路由或 shadcn/ui 组件的复杂 artifacts，不适用于简单的单文件 HTML/JSX artifacts。
license: Complete terms in LICENSE.txt
---

# Artifacts Builder (Artifacts 构建器)

要构建强大的前端 claude.ai artifacts，请遵循以下步骤：
1. 使用 `scripts/init-artifact.sh` 初始化前端仓库
2. 通过编辑生成的代码来开发你的 artifact
3. 使用 `scripts/bundle-artifact.sh` 将所有代码打包成单个 HTML 文件
4. 向用户展示 artifact
5. (可选) 测试 artifact

**技术栈**: React 18 + TypeScript + Vite + Parcel (打包) + Tailwind CSS + shadcn/ui

## 设计与风格指南

非常重要：为了避免通常被称为 "AI 垃圾 (AI slop)" 的情况，请避免使用过多的居中布局、紫色渐变、统一的圆角和 Inter 字体。

## 快速开始

### 第 1 步：初始化项目

运行初始化脚本以创建一个新的 React 项目：
```bash
bash scripts/init-artifact.sh <project-name>
cd <project-name>
```

这将创建一个配置完整的项目，包含：
- ✅ React + TypeScript (通过 Vite)
- ✅ Tailwind CSS 3.4.1 配备 shadcn/ui 主题系统
- ✅ 已配置路径别名 (`@/`)
- ✅ 预装 40+ shadcn/ui 组件
- ✅ 包含所有 Radix UI 依赖项
- ✅ 已配置 Parcel 用于打包 (通过 .parcelrc)
- ✅ Node 18+ 兼容性 (自动检测并固定 Vite 版本)

### 第 2 步：开发你的 Artifact

要构建 artifact，请编辑生成的文件。请参阅下方的 **常见开发任务** 以获取指导。

### 第 3 步：打包为单个 HTML 文件

要将 React 应用打包为单个 HTML artifact：
```bash
bash scripts/bundle-artifact.sh
```

这将创建 `bundle.html` - 一个自包含的 artifact，其中内联了所有 JavaScript、CSS 和依赖项。此文件可以直接作为 artifact 在 Claude 对话中共享。

**要求**：你的项目根目录下必须有一个 `index.html`。

**脚本的作用**：
- 安装打包依赖项 (parcel, @parcel/config-default, parcel-resolver-tspaths, html-inline)
- 创建带有路径别名支持的 `.parcelrc` 配置
- 使用 Parcel 构建 (无 source maps)
- 使用 html-inline 将所有资源内联到单个 HTML 中

### 第 4 步：与用户共享 Artifact

最后，在对话中与用户共享打包后的 HTML 文件，以便他们可以将其作为 artifact 查看。

### 第 5 步：测试/可视化 Artifact (可选)

注意：这是一个完全可选的步骤。仅在必要或被请求时执行。

要测试/可视化 artifact，请使用可用工具（包括其他 Skills 或内置工具如 Playwright 或 Puppeteer）。通常，避免预先测试 artifact，因为这会增加请求与看到完成 artifact 之间的延迟。如果被请求或出现问题，请在展示 artifact 后再进行测试。

## 参考

- **shadcn/ui 组件**: https://ui.shadcn.com/docs/components
