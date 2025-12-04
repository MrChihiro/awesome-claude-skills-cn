---
name: webapp-testing
description: 使用 Playwright 交互和测试本地 Web 应用程序的工具包。支持验证前端功能、调试 UI 行为、捕获浏览器屏幕截图和查看浏览器日志。
license: Complete terms in LICENSE.txt
---

# Web 应用程序测试

要测试本地 Web 应用程序，请编写原生 Python Playwright 脚本。

**可用的辅助脚本**：
- `scripts/with_server.py` - 管理服务器生命周期（支持多个服务器）

**始终首先使用 `--help` 运行脚本**以查看用法。不要阅读源代码，除非你先尝试运行脚本并发现绝对需要自定义解决方案。这些脚本可能非常大，因此会污染你的上下文窗口。它们的存在是为了作为黑盒脚本直接调用，而不是摄入到你的上下文窗口中。

## 决策树：选择你的方法

```
User task → Is it static HTML?
    ├─ Yes → Read HTML file directly to identify selectors
    │         ├─ Success → Write Playwright script using selectors
    │         └─ Fails/Incomplete → Treat as dynamic (below)
    │
    └─ No (dynamic webapp) → Is the server already running?
        ├─ No → Run: python scripts/with_server.py --help
        │        Then use the helper + write simplified Playwright script
        │
        └─ Yes → Reconnaissance-then-action:
            1. Navigate and wait for networkidle
            2. Take screenshot or inspect DOM
            3. Identify selectors from rendered state
            4. Execute actions with discovered selectors
```

## 示例：使用 with_server.py

要启动服务器，请先运行 `--help`，然后使用助手：

**单个服务器：**
```bash
python scripts/with_server.py --server "npm run dev" --port 5173 -- python your_automation.py
```

**多个服务器（例如，后端 + 前端）：**
```bash
python scripts/with_server.py \
  --server "cd backend && python server.py" --port 3000 \
  --server "cd frontend && npm run dev" --port 5173 \
  -- python your_automation.py
```

要创建自动化脚本，仅包含 Playwright 逻辑（服务器会自动管理）：
```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=True) # Always launch chromium in headless mode
    page = browser.new_page()
    page.goto('http://localhost:5173') # Server already running and ready
    page.wait_for_load_state('networkidle') # CRITICAL: Wait for JS to execute
    # ... your automation logic
    browser.close()
```

## 侦察-然后-行动模式

1. **检查渲染的 DOM**：
   ```python
   page.screenshot(path='/tmp/inspect.png', full_page=True)
   content = page.content()
   page.locator('button').all()
   ```

2. 从检查结果中**识别选择器**

3. 使用发现的选择器**执行操作**

## 常见陷阱

❌ **不要**在动态应用上等待 `networkidle` 之前检查 DOM
✅ **务必**在检查之前等待 `page.wait_for_load_state('networkidle')`

## 最佳实践

- **将捆绑脚本用作黑盒** - 要完成任务，请考虑 `scripts/` 中可用的脚本之一是否可以提供帮助。这些脚本可靠地处理常见的复杂工作流，而不会弄乱上下文窗口。使用 `--help` 查看用法，然后直接调用。
- 对同步脚本使用 `sync_playwright()`
- 完成后始终关闭浏览器
- 使用描述性选择器：`text=`, `role=`, CSS 选择器或 ID
- 添加适当的等待：`page.wait_for_selector()` 或 `page.wait_for_timeout()`

## 参考文件

- **examples/** - 显示常见模式的示例：
  - `element_discovery.py` - 发现页面上的按钮、链接和输入
  - `static_html_automation.py` - 对本地 HTML 使用 file:// URL
  - `console_logging.py` - 在自动化期间捕获控制台日志
