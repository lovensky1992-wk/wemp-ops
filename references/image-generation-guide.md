# 配图生成完整指南

> 从封面图到正文配图到产品截图的完整操作手册。
> 被 SKILL.md Step 4（封面与配图）引用。

## 封面图

设计指南见 `cover-image-guide.md`（六维度体系：Type/Palette/Rendering/Text/Mood/Font + 12 个预设 + 兼容矩阵 + 构图核心原则）。三种方案按优先级：

**方案 A（优先）：idealab Chat API**
- `<WORKSPACE>/scripts/generate-image.sh --prompt "prompt" --filename output.jpg`
- 默认模型 `gemini-3.1-flash-image-preview`，团队 AK 免费，走 /chat/completions 接口
- 2.35:1 裁剪：生成后 `sips -c 1090 2560 output.jpg`
- 超时/报错时脚本自动降级到 Gemini Key 轮换
- ⚠️ 不用 emoji（浏览器截图会变色块），用纯文字 + 几何图形

**方案 B（降级）：Seedream 5.0 Lite**
- `<WORKSPACE>/scripts/seedream-generate.sh "prompt" output.jpg "2560x1440" 1`
- 0.22 元/张，idealab 不稳定时使用
- 裁剪同方案 A：`sips -c 1090 2560 output.jpg`

**方案 C（兜底）：HTML 渲染 + 浏览器截图**
- 写一个 HTML 页面（渐变背景 + 标题文字 + SVG 图形）
- 用 `python3 -m http.server` 本地启动
- 用 browser 工具 navigate + screenshot 截图
- 适用于需要精确控制布局时

## 配图规划与生成

完整指南见 `illustration-prompts.md`（Type×Style 矩阵、Prompt 规范、风格锚点）。

### 配图规划（先规划再生图）

1. **扫描文章结构**，按以下规则标注潜在配图位置：
   - `##` 标题后的第一段 → 潜在配图点
   - 概念首次出现 → 用插图辅助解释
   - 转折/对比处（"但是"、"然而"、"相比之下"）→ 适合对比图
   - 连续超 800 字无任何视觉元素 → 需要打断

2. **内容信号自动匹配**，根据段落关键词推荐 Type：
   - 架构/分层/系统 → `framework` | 步骤/流程 → `flowchart` | vs/对比 → `comparison`
   - 数据/百分比 → `infographic` | 叙事/经历 → `scene` | 代码/界面 → `screenshot`

3. **锁定全文 Style**（一篇文章只用一种 AI 生图风格，从 `cover-image-guide.md` 预设中选）：
   - 技术/产品文 → `ai-product`（默认）| 数据/架构文 → `dashboard` | 故事/教育文 → `pm-growth` | 观点文 → `bold-opinion`

4. **输出配图计划表**（保存到 `illustration-plan.md`），让老板确认后再生图。
   密度参考：2000 字 3 张、3000 字 4-5 张，正文配图硬上限 5 张。

### 生图执行

配图有两条渲染路径，在配图计划表中按每张图标注：

**路径 A：AI 生图**（视觉美感优先，适合大部分场景）
- **优先级**：idealab Image API → Seedream 5.0 Lite → Gemini 生图 → ComfyUI
  - idealab（首选）: `<WORKSPACE>/scripts/generate-image.sh --prompt "prompt" --filename output.jpg --size 2560x1440`
    - 默认模型 `gemini-3.1-flash-image-preview`，团队AK免费；超时/报错自动降级到 Gemini
  - Seedream（降级）: `<WORKSPACE>/scripts/seedream-generate.sh "prompt" output.jpg "2560x1440"`
  - 正文插图 16:9 `2560x1440`
- **Prompt 按 LDSCS-R 六层结构构造**：Layout → Data → Semantics → Characters → Style → Ratio
- **风格锚点**：第一张图成功后，记录风格特征到 `prompts/style-anchor.md`，后续图片引用保持一致
- **Prompt 持久化**：每张图的 prompt 保存到 `prompts/NN-{type}-{slug}.md`，便于回溯修改

**路径 B：Mermaid 渲染截图**（信息精确性优先，技术文章的流程/架构/对比图）
- **适用条件**：配图计划中 Style 标注为 `mermaid-render` 的插图
- **工作流**：
  1. 生成 Mermaid 代码（遵守 `illustration-prompts.md` 中的 Mermaid 规范）
  2. 写入 `<WORKSPACE>/scripts/mermaid-render.html`（临时 HTML 模板）
  3. 浏览器打开 → resize 2560x1440 → screenshot
  4. 裁剪白边（如需要）→ 存入 `images/`
- **Mermaid prompt 也持久化**：保存到 `prompts/NN-{type}-{slug}.md`，记录 Mermaid 源码

**通用规则**：
- 截图美化：`<WORKSPACE>/scripts/beautify-screenshot.sh <input> [output] --shadow --bg "#f5f5f5"`
- 水印去除：`<WORKSPACE>/scripts/remove-watermark.sh <input> [output]`（Gemini 生图 需去水印）
- 配图数量：宁缺毋滥。不确定要不要配图 → 不配。
- 同一篇文章中路径 A 和路径 B 可以混用，但渲染方式不超过 2 种。

## 产品截图获取

文章涉及线上产品（AI 工具、SaaS 产品等）时，截取真实产品界面作为配图。

**公开页面（无需登录）：**
```bash
# 1. 打开产品页面
browser action:open url:"https://example.com/product"

# 2. 等待加载完成后截图
browser action:screenshot fullPage:false type:png

# 3. 裁剪/缩放（macOS sips 工具）
sips -z <高度> <宽度> screenshot.png                    # 缩放
sips -c <高度> <宽度> screenshot.png                    # 裁剪居中
sips --resampleWidth 800 screenshot.png                  # 按宽度等比缩放

# 4. 上传到微信素材库
node scripts/publisher.mjs  # 通过 --markdown 自动上传
# 或手动：在 utils.mjs 中调用 uploadArticleImage()
```

**需登录页面（付费产品/内部系统）：**
1. 让用户在 Chrome 打开目标页面
2. 用户点击 OpenClaw Browser Relay 工具栏图标 attach 该 tab
3. `browser action:screenshot profile:chrome` 截图
4. 截图后同上流程裁剪上传

**截图规范：**
- 宽度 600-900px，避免过大（微信有尺寸限制）
- 隐藏/打码敏感信息（用户名、私有数据等）
- 浏览器地址栏按需保留（能说明产品来源时保留）
- 优先截取核心功能区域，不截全屏
- 深色/浅色主题根据文章风格选择
