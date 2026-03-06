---
name: wemp-ops
description: >
  微信公众号全流程运营：选题→采集→写作→排版→发布→数据分析→评论管理。
  触发词：写公众号文章、写一篇关于XXX的文章、采集热点、公众号日报、公众号周报、
  检查评论、回复评论、发布文章、推送到公众号、公众号数据、生成文章。
  当用户给出选题方向时，自动完成素材采集→内容写作→封面生图→排版美化→推送草稿箱全流程。
---

# wemp-ops — 微信公众号运营技能

## 环境检查

首次使用前执行：
```bash
node scripts/setup.mjs
```

检查 Node.js 版本、Python3、微信公众号 API 配置。

## 工作流路由

根据用户意图选择对应流程：

| 意图 | 流程 |
|------|------|
| "写一篇关于 X 的文章" | → **全流程**（下方详述） |
| "采集 X 热点" | → 仅采集 |
| "公众号日报/周报" | → 数据分析 |
| "检查/回复评论" | → 互动管理 |
| "发布文章" | → 仅发布 |

## 全流程：选题到草稿箱

当用户给出选题方向时，执行以下完整流程。先读 `persona.md` 确定写作人设。

### Step 1: 理解选题

读 `references/article-templates.md` 判断内容类型：

- **AI 产品拆解** — 具体产品名 + 分析/拆解
- **场景解决方案** — "怎么用 AI 做 XXX"
- **效率提升实战** — 工具 + 技巧/心得
- **产品方法论** — 抽象话题 + 思考
- **行业观察** — 新闻/趋势 + 观点

选题模糊时给 2-3 个具体方向让用户选（最多 1 轮澄清）。

### Step 2: 素材采集

**2a. 收藏库检索（优先）**
先从个人收藏库中检索相关素材，这些是已经筛选过的高质量内容：
1. 标签匹配：`grep -i "关键词" ~/.openclaw/workspace/collections/tags.md`
2. 全文搜索：`grep -ril "关键词" ~/.openclaw/workspace/collections/`
3. 有匹配时，读取对应文件的核心观点、要点摘录、个人笔记
4. 收藏素材可直接引用观点、数据，但需注明出处

**2b. 外部采集（补充）**
收藏库素材不足时，从外部补充：
1. 根据选题扩展 3-5 个搜索关键词
2. `web_search` 搜索 2-3 轮（官方信息→深度分析→对比评测）
3. `web_fetch` 抓取 2-4 篇高质量参考文章
4. 可选：`node scripts/smart_collect.mjs` 从 20+ 数据源采集相关热点
5. 提取关键事实、数据、观点备用

**2c. 素材整理**
合并收藏库 + 外部素材，按相关度排序，标注来源

### Step 3: 写作

读 `references/writing-sop.md` 和 `references/style-guide.md`，按以下要求写作：

- 遵循 `persona.md` 人设（AI 产品经理第一人称）
- 按 `references/article-templates.md` 对应类型的结构模板
- 2000-3000 字，短句为主
- 链接用纯文本格式
- 输出为 Markdown 文件，保存到工作目录
- **不要在文中出现 H1 标题**（公众号自带标题，正文从 H2 开始）

#### ⚠️ 写作红线（必须遵守）

- **绝不暴露 AI 参与写作**：不说"这篇文章是 AI 写的"、"让 AI 帮我写"等。读者不喜欢 AI 文章
- **讲故事，不讲论点**：用时间线、场景、情绪推进，不用"总结"、"核心观点"、编号式论点堆砌
- **自然过渡**：不用中括号小标题、不用"以下是 N 条心得"式结构
- **让读者感受到力量**：分享经历，不是教学。有踩坑有收获，有真实细节

### Step 4: 封面图

设计指南见 `references/cover-image-guide.md`。两种方案：

**方案 A（优先）：nano-banana-pro 生成**
- 根据内容类型选配色
- 2.35:1 横版，中文标题 + 副标题
- ⚠️ 不用 emoji（浏览器截图会变色块），用纯文字 + 几何图形

**方案 B（备选）：HTML 渲染 + 浏览器截图**
- 写一个 HTML 页面（渐变背景 + 标题文字 + SVG 图形）
- 用 `python3 -m http.server` 本地启动
- 用 browser 工具 navigate + screenshot 截图
- 适用于 Gemini 额度不足或需要精确控制布局时

### Step 4.5: 正文配图

**原则：真实截图 > AI 信息图 > 不放图**

详细风格模板和 Prompt 见 `references/illustration-prompts.md`。

配图决策：
```
有真实的终端/代码/产品界面？ → 真实截图 + 美化（scripts/beautify-screenshot.sh --shadow）
有概念/流程需要解释？ → Notion 手绘信息图（nano-banana-pro）
有数据对比/技术架构？ → 扁平科技信息图（nano-banana-pro）
文章内容简单？ → 不放图，避免凑数
```

截图美化：`~/.openclaw/workspace/scripts/beautify-screenshot.sh <input> [output] --shadow --bg "#f5f5f5"`
水印去除：`~/.openclaw/workspace/scripts/remove-watermark.sh <input> [output]`（AI 生图必须去水印）

配图数量：2-4 张，宁缺毋滥。同一篇文章的 AI 生图在同一次对话中生成，保持风格一致。

### Step 4.6: 产品截图获取

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

### Step 5: 排版美化

```bash
# 基础排版
python3 scripts/markdown_to_html.py --input article.md --theme tech --output article.html

# 带图片自动上传（本地图片自动上传到微信素材库并替换 URL）
python3 scripts/markdown_to_html.py --input article.md --theme tech --output article.html --upload
```

主题选择：tech（科技风，默认）、minimal（简约风）、business（商务风）。
排版约束详见 `references/weixin-constraints.md`。

如果有额外配图需要手动插入（非 Markdown 内嵌图片），先上传再手动插入 HTML。

### Step 6: 推送草稿箱

```bash
# 一键从 Markdown 到草稿（推荐，自动转 HTML + 上传图片 + 清理旧同名草稿）
node scripts/publisher.mjs --markdown article.md --title "文章标题" --cover cover.png

# 或手动分步：先转 HTML 再推送
python3 scripts/markdown_to_html.py --input article.md --theme tech --output article.html --upload
node scripts/publisher.mjs --title "文章标题" --content article.html --cover cover.png

# 跳过自动清理旧草稿
node scripts/publisher.mjs --markdown article.md --title "标题" --cover cover.png --no-cleanup

# 列出草稿
node scripts/publisher.mjs --list

# 删除草稿
node scripts/publisher.mjs --delete --media-id <id>

# 发布草稿（用户确认后）
node scripts/publisher.mjs --publish --media-id <草稿media_id>
```

**默认停在草稿箱，不自动发布。** 告知用户草稿已创建，确认后再发布。
推送新版本时自动清理同标题旧草稿（`--no-cleanup` 跳过）。

### Step 7: 交付

向用户汇报：文章标题、字数、草稿状态、封面预览、建议发布时间。

## 仅采集

```bash
node scripts/smart_collect.mjs --query "用户需求" --keywords "AI扩展的关键词" --sources "hackernews,v2ex,36kr" [--deep]
```

数据源分类：
- `tech`: hackernews, github, v2ex, sspai, juejin, ithome, producthunt
- `china`: weibo, zhihu, baidu, douyin, bilibili, toutiao, tencent, thepaper, hupu
- `finance`: 36kr, wallstreetcn, cls

采集后整理为选题候选清单，每条含：标题、来源、热度、链接、与用户需求的相关度。

## 数据分析

```bash
# 日报（默认昨天）
node scripts/daily_report.mjs [--date YYYY-MM-DD]

# 周报
node scripts/weekly_report.mjs
```

输出包含：用户增长、阅读数据、热门文章、互动数据、AI 洞察。

## 互动管理

```bash
# 检查新评论
node scripts/check_comments.mjs

# 回复评论
node scripts/reply_comment.mjs --comment-id <id> --content "回复内容"
```

AI 生成回复建议时遵循 `persona.md` 的语气规范，用户确认后再执行回复。

## 配置

公众号凭证配置在 **skill 自己的** `config/default.json`：

```json
{
  "weixin": {
    "appId": "你的AppID",
    "appSecret": "你的AppSecret"
  }
}
```

⚠️ **不要写到 `openclaw.json` 的 `channels` 里！** `channels` 只接受 OpenClaw 内置渠道类型（dingtalk/telegram/discord 等），写入未知类型会导致 gateway 校验失败并不断重启。

其他配置（数据源偏好、报告时间等）同样在 `config/default.json` 中调整。
