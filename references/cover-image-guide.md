# 封面图设计指南

## 七维度选择体系

封面图由 7 个独立维度交叉定义，外加一个可选的 Art Reference 锚点层。每个维度独立选择，通过兼容矩阵确保组合合理。

```
文章内容 → 自动推荐七维度组合 → [可选] 叠加 Art Reference → 老板确认/调整 → 组装 prompt → 生成
```

---

### 维度 1：构图类型（Type）

| 类型 | 构图方式 | 视觉区占比 | 适用文章 |
|------|---------|-----------|---------|
| `hero` | 大视觉冲击 + 标题覆盖，戏剧性构图 | 视觉 60-70% | 产品分析、重磅发布 |
| `conceptual` | 抽象概念可视化，信息分区，干净 | 视觉 50% | 技术架构、方法论 |
| `typography` | 文字为主体元素（40%+面积），极少视觉 | 文字 60% | 观点文、金句、声明 |
| `metaphor` | 具象物体隐喻抽象概念，符号化 | 视觉 60% | 成长、转型、哲理 |
| `split` | 左右或上下对比分屏，强烈视觉对照 | 各 50% | 对比文、before/after |
| `minimal` | 单一焦点 + 大量留白（60%+） | 视觉 30% | 极简核心概念、禅意 |

### 维度 2：配色方案（Palette）

| 配色 | 色值 | 视觉感受 | 适用 |
|------|------|---------|------|
| `tech-blue` | #1a1f5c → #7c3aed | 科技/紫蓝渐变 | AI产品、技术拆解 |
| `insight-blue` | #1e3a5f → #3b82f6 | 理性/深蓝 | 方法论、框架思考 |
| `action-orange` | #f97316 → #eab308 | 活力/橙黄 | 效率提升、实战 |
| `solution-green` | #10b981 → #f97316 | 解决方案/绿橙 | 场景方案、破局 |
| `trend-cyan` | #0891b2 → #06b6d4 | 趋势/蓝绿 | 行业观察、前沿 |
| `mono` | #1A1A1A + #F5F5F5 | 极简/黑白灰 | 哲理、极简、金句 |
| `warm` | #F5E6D0 + #D4956A + #7BA3A8 | 温暖/莫兰迪 | 个人故事、感悟 |
| `dark` | #0F172A + #3B82F6 + #06B6D4 | 高级/深色 | 电影感、高级观点 |
| `gallery` | #2C2C2C + #F5F0E8 + #C8A96E | 美术馆/画廊感（深灰+米白+金） | 深度文章、文化品味 |
| `monet` | #6B9BC3 + #F4E8C1 + #A8C97F + #E8B87C | 印象派色系（蓝天+暖光+绿荫+赭） | 洞察类、趋势观察 |
| `pop` | #FF1744 + #FFEA00 + #2979FF + #000000 | 波普艺术（高饱和红黄蓝+黑） | 争议观点、打破认知 |
| `edo` | #2D4A3E + #C8553D + #F2E8CF + #1B1B1B | 江户色（靖蓝+朱红+素纸+墨） | 东方叙事、方法论 |
| `darkroom` | #1A1A1A + #F5F5F5 + #D4A574 | 暗房/胶片感（纯黑+高光+暖褐） | 个人故事、纪实感 |

### 维度 3：渲染风格（Rendering）

| 渲染 | 视觉特征 | Prompt 关键词 |
|------|---------|-------------|
| `3d-icon` | 现代3D图标、光效、微渐变 | modern 3D style icons, subtle glow, depth |
| `flat-vector` | 扁平矢量、干净线条、无阴影 | flat vector, clean lines, no shadows, solid colors |
| `hand-drawn` | 手绘马克笔、不均匀线条 | hand-drawn marker style, uneven strokes, sketch quality |
| `painterly` | 水彩/油画质感、柔和边缘、艺术感 | watercolor soft edges, painterly brushstrokes, dreamy artistic |
| `digital` | 数据可视化、仪表盘风、打磨感 | polished digital render, data dashboard aesthetic, clean gradients |
| `screen-print` | 丝网印刷、半色调、2-4色 | screen print poster art, halftone dots, 2-4 flat colors, stencil-cut |
| `chalk` | 黑板粉笔、教学感、粗糙质感 | chalkboard style, chalk texture, rough hand-lettering, dark background |
| `oil-painting` | 油画厚涂笔触、古典光影、画廊质感 | oil painting impasto, visible brushstrokes, Renaissance lighting, gallery-quality, rich texture |
| `ukiyo-e` | 浮世绘木版画、平面色块、勾线描边、和风 | ukiyo-e woodblock print style, flat bold colors, black outlines, wave patterns, Japanese aesthetic |
| `collage` | 拼贴风、杂志剪报、纹理叠加、错位排列 | mixed-media collage, magazine cutouts, torn paper edges, layered textures, found objects |
| `risograph` | Riso印刷、半透明色层叠加、颗粒感、限色2-3色 | risograph print, limited 2-3 color overlay, grain texture, misregistration, indie press feel |
| `ink-wash` | 水墨写意、留白呼吸、浓淡干湿、气韵 | Chinese ink wash painting, sumi-e, elegant emptiness, bold-thin brush contrast, zen atmosphere |
| `poster-art` | 复古海报、强字体排版、大色块、宣传画感 | vintage poster art, bold typography, limited palette, propaganda style, strong visual hierarchy |

### 维度 4：文字密度（Text）

| 级别 | 文字内容 | 适用 |
|------|---------|------|
| `none` | 纯视觉，无文字 | 抽象概念封面（少用） |
| `title-only` | 仅主标题（**默认**） | 大多数文章 |
| `title-subtitle` | 主标题 + 副标题/系列名 | 系列文章、教程 |
| `text-rich` | 标题 + 副标题 + 2-4 关键词标签 | 公告、多要点文章 |

### 维度 5：视觉强度（Mood）

| 级别 | 效果 | 量化调整 | 适用 |
|------|------|---------|------|
| `subtle` | 低对比、柔和、专业克制 | 对比度 -20~30%，饱和度 -20~30%，线条更细 | 方法论、学术类 |
| `balanced` | 中等对比（**默认**） | 标准 | 大多数文章 |
| `bold` | 高对比、强冲击、饱和色 | 对比度 +20~30%，饱和度 +20~30%，线条更粗 | 重磅观点、争议话题 |

### 维度 6：字体风格（Font）← 新增

| 字体 | 视觉感受 | Prompt 关键词 | 适用 |
|------|---------|-------------|------|
| `clean` | 无衬线、现代、干净（**默认**） | clean sans-serif typography | 技术、产品、大多数文章 |
| `handwritten` | 手写体、亲和、个人感 | handwritten casual font style | 个人故事、生活感悟 |
| `serif` | 衬线体、经典、学术感 | classic serif editorial typography | 深度长文、学术、书评 |
| `display` | 粗重装饰体、冲击力 | bold decorative display font | 公告、事件、促销类 |

---

### 维度 7：布局策略（Layout）

封面图在微信生态中有多种裁切场景，布局策略决定核心信息在不同场景下的完整性。

| 布局 | 构图方式 | 安全区处理 | 适用 |
|------|---------|-----------|------|
| `centered` | 标题+视觉元素全部居中，填满安全区 | 安全区=核心内容区 | 大多数文章（**默认**） |
| `full-bleed` | 视觉铺满整个 900×383，标题叠加在画面上 | 标题仍在安全区，背景可出界 | 视觉冲击类（hero/metaphor） |
| `split` | 左右或上下对比分屏 | ☦️ 标题必须在中间偏左，不能完全靠左 | 对比/产品类（split） |

**Layout 与 Type 的强绑定：**

| Type | 推荐 Layout | 原因 |
|------|------------|------|
| `hero` | full-bleed | 视觉铺满才有冲击力 |
| `conceptual` | centered | 概念图+标题居中最稳 |
| `typography` | centered | 文字本身就是主体 |
| `metaphor` | full-bleed | 隐喻物体需要画面空间 |
| `split` | split | 对比就是分区 |
| `minimal` | centered | 留白的核心在居中 |

---

### 可选层：Art Reference（艺术锚点）

Art Reference 是叠加在七维度之上的可选层，用名画/艺术运动的视觉语言提升封面的文化感和趣味性。

**使用规则：**
1. Art Reference 是可选的——大多数文章用普通七维度就够了
2. 触发条件：文章主题有“跨界”、“打破常规”、“深度思考”、“文化”、“趋势变革”属性时推荐
3. 不是直接复刻名画：而是提取名画的**视觉语言**（色调、笔触、构图、氛围）融入封面
4. 前景文字必须清晰：名画元素只作为背景/纹理层，标题区域强制高对比

#### Art Reference 预设库

| Reference ID | 名画/艺术运动 | 视觉锚点 | 封面中的用法 | 推荐搭配 |
|---|---|---|---|---|
| `starry-night` | 梵高《星空》 | 漩涡笔触、深蓝+金黄色调、流动感 | 漩涡笔触铺满背景，前景简洁标题 | oil-painting + gallery, Layout=full-bleed |
| `great-wave` | 葛饰北斋《神奈川冲浪里》 | 浪花线条、蓝白对比、动势强 | 浪花作为视觉主体，标题嵌入留白处 | ukiyo-e + edo, Layout=full-bleed |
| `mondrian` | 蒙德里安 格子画 | 红黄蓝+黑色网格、几何分割 | 用色块分割封面信息区域 | flat-vector + pop, Layout=centered |
| `warhol` | 沃霍尔 波普 | 重复图像、撞色、丝网印刷感 | 核心概念重复排列+颜色变体 | risograph + pop, Layout=centered |
| `monet-garden` | 莫奈《睡莲》《日出·印象》 | 光影斑驳、色彩晕染、模糊边缘 | 梦幻背景底，前景高对比文字 | oil-painting + monet, Layout=full-bleed |
| `song-dynasty` | 宋代山水（范宽/郭熙） | 气韵留白、山石皴法、淡墨层次 | 大面积留白+角落意境元素，标题居中 | ink-wash + edo/gallery, Layout=centered |
| `bauhaus` | 包豪斯 | 几何形状、原色、功能至上 | 几何图形组织信息层级 | flat-vector/poster-art + pop, Layout=centered |
| `film-noir` | 黑色电影 | 强明暗对比、剪影、戏剧光 | 人物/物体剪影+光束，标题嵌入暗部 | digital + darkroom, Layout=full-bleed |

#### Art Reference 与布局的搭配指导

| Art Reference | 推荐 Layout | 名画元素放哪 | 标题放哪 |
|---|---|---|---|
| `starry-night` | full-bleed | 漩涡笔触铺满背景 | 安全区内，叠深色半透明遮罩 |
| `great-wave` | full-bleed | 浪花占据右侧+上方 | 安全区左下角，避开浪花区域 |
| `mondrian` | centered | 色块网格作为信息分区 | 在最大色块内 |
| `warhol` | centered | 重复图案在安全区内排列 | 顶部或底部条幅区域 |
| `monet-garden` | full-bleed | 印象派色彩铺满背景 | 安全区内，底部暗色带+白字 |
| `song-dynasty` | centered | 留白即构图，意境元素在角落 | 安全区正中，大字+大留白 |
| `bauhaus` | centered | 几何色块分割版面 | 在主色块区域内 |
| `film-noir` | full-bleed | 强光影/剪影铺满 | 安全区内高亮区域 |

#### Art Reference 与 Rendering 兼容矩阵

| Rendering \ Art Ref | starry-night | great-wave | mondrian | warhol | monet-garden | song-dynasty | bauhaus | film-noir |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `oil-painting` | ✓✓ | ✗ | ✗ | ✗ | ✓✓ | ✗ | ✗ | ✗ |
| `ukiyo-e` | ✗ | ✓✓ | ✗ | ✗ | ✗ | ✓ | ✗ | ✗ |
| `collage` | ✓ | ✓ | ✓ | ✓✓ | ✓ | ✗ | ✓ | ✓ |
| `risograph` | ✗ | ✗ | ✓ | ✓✓ | ✗ | ✗ | ✓✓ | ✗ |
| `ink-wash` | ✗ | ✓ | ✗ | ✗ | ✗ | ✓✓ | ✗ | ✗ |
| `poster-art` | ✗ | ✗ | ✓✓ | ✓ | ✗ | ✗ | ✓✓ | ✓ |
| `flat-vector` | ✗ | ✗ | ✓✓ | ✗ | ✗ | ✗ | ✓✓ | ✗ |
| `digital` | ✗ | ✗ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓✓ |
| `3d-icon` | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| `hand-drawn` | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| `screen-print` | ✗ | ✗ | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ |
| `chalk` | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| `painterly` | ✓ | ✗ | ✗ | ✗ | ✓✓ | ✓ | ✗ | ✗ |

> ✓✓ 强推荐 | ✓ 可用 | ✗ 不推荐

---

## 构图核心原则（融合 baoyu-cover-image Base Prompt）

每次生成封面图，prompt 末尾必须附加以下构图约束：

```
Composition rules for WeChat Official Account cover (900×383 display, 2.35:1):
- SAFE ZONE: All text and critical visual elements MUST be within the center 383×383 square area
  (the image will be center-cropped to 1:1 in share cards and history list)
- Left and right margins (~258px each at 900px width) are "lossy zones" — decorative only, no key info
- Text padding: minimum 30px from any edge
- Thumbnail test: title must remain legible when displayed at 200px width (use large bold font)
- Background visual CAN extend to full width, but core message stays centered
- If using art reference background: apply 40-60% dark/light overlay on text area for contrast
- Visual anchor: main element centered or offset within safe zone
- Information hierarchy: one dominant focal point, 1-2 supporting elements, decorative accents
- Clean or art-reference backgrounds, no cluttered/busy competing elements in text zone
- Characters: simplified silhouettes only, NO realistic human faces or bodies
- Chinese text must be clearly readable, text and visuals must not overlap
- No emoji (renders as color blocks in browser screenshots)
- Horizontal layout, high quality
```

### 安全区示意图

```
┌──────────────────────────────────────────────────────────┐
│ ←258px→ ┌──────────────────────┐ ←258px→ │
│  可丢失   │                      │  可丢失   │  900×383
│  装饰区   │   383×383 安全区      │  装饰区   │  (2.35:1)
│          │   核心标题+视觉       │          │
│          │   必须在这里          │          │
│          └──────────────────────┘          │
└──────────────────────────────────────────────────────────┘
```

**安全区规则：**
- 头条大图（订阅号消息列表）：全幅 900×383 完整显示
- 历史文章列表 / 朋友圈分享卡 / 对话框分享：居中裁切为 1:1 方图（只显示中间 383×383）
- 次条/多条：独立 200×200 正方形（另外制作）

### 图标词汇表速查

| 类别 | 图标 |
|------|------|
| 技术 | 代码窗口、齿轮、电路、云、锁、API 括号 |
| 创意 | 灯泡、火箭、靶心、拼图、钥匙、放大镜 |
| 沟通 | 对话气泡、聊天点、喇叭、信封 |
| 成长 | 植物/幼苗、树、箭头、图表、山 |
| 工具 | 扳手、铅笔、画笔、清单、时钟 |
| 抽象概念 | 无穷≡、太极、螺旋、层叠/堆叠、桥、门/传送门、镜子/倒影 |

### 图标组合模式

通过组合图标创建视觉比喻：

| 组合 | 表达 |
|------|------|
| 灯泡 + 齿轮 | 创新工程 |
| 植物 + 代码 | 有机技术增长 |
| 火箭 + 靶心 | 精准加速 |
| 钥匙 + 锁 | 安全解决方案 |
| 桥 + 人物 | 团队连接 |
| 放大镜 + 数据 | 分析洞察 |

### 渲染风格与图标处理

| Rendering | 图标风格 |
|-----------|----------|
| `3d-icon` | 立体感、微渐变、光影 |
| `flat-vector` | 几何化、简单形状、均匀填充 |
| `hand-drawn` | 涂鸦感、有机线条、手绘质感 |
| `painterly` | 柔和边缘、笔触感 |
| `digital` | 精确、微渐变、打磨 |
| `screen-print` | 模板切割、单色块、半色调 |
| `chalk` | 粗糙、粉笔质感、网格对齐 |

---

## Rendering 详细定义

每种渲染风格的线条/纹理/深度/元素规范，prompt 中引用对应条目：

| Rendering | Lines | Texture | Depth | Prompt 特征词 |
|-----------|-------|---------|-------|---------------|
| `3d-icon` | 干净圆滑 | 微光泰效果 | 有立体感和阴影 | modern 3D icons, subtle glow, soft shadows, depth layers |
| `flat-vector` | 均匀精确、无变化 | 无纹理、纯色填充 | 完全扁平 | flat vector, clean uniform lines, solid fills, no shadows, no gradients |
| `hand-drawn` | 不均匀、略有抖动 | 马克笔/铅笔质感 | 最小深度 | hand-drawn marker sketch, slightly shaky lines, paper texture, doodle quality |
| `painterly` | 柔和笔触、模糊边缘 | 水彩/油画质感 | 柔和边缘、光影渗透 | watercolor soft washes, visible brushstrokes, dreamy blending, artistic texture |
| `digital` | 精确干净、圆滑 | 微光泰效果 | 微层次感 | polished digital render, clean gradients, dashboard aesthetic, subtle depth |
| `screen-print` | 模板切割、粗犷 | 半色调点/色块边缘 | 扁平、无深度 | screen print poster, halftone dots, 2-4 flat colors, stencil-cut edges, bold contrast |
| `chalk` | 粗糙手写、不均匀 | 粉笔飞粉感 | 扁平 | chalkboard style, chalk dust texture, rough hand-lettering, dark background, educational feel |
| `oil-painting` | 厚重笔触、可见笔痕 | 油画堆叠质感 | 深度感、古典光影 | oil painting impasto, visible thick brushstrokes, Renaissance chiaroscuro lighting, gallery museum quality, rich layered texture |
| `ukiyo-e` | 精确勾线、均匀轮廓 | 木版印刷纹理、平面填色 | 完全扁平、无深度 | ukiyo-e woodblock print, flat bold color fills, precise black outlines, wave/cloud patterns, Japanese Edo period aesthetic |
| `collage` | 不规则边缘、擕裂感 | 报纸剪报/纸张纹理/胶带痕迹 | 多层叠加、错位 | mixed-media collage, magazine cutouts, torn paper edges, masking tape, layered found objects, intentional misalignment |
| `risograph` | 略有偏移的色层边缘 | 粗颗粒、半透明色块 | 扁平、色层叠加产生混色 | risograph print, 2-3 spot color overlay, grain texture, slight misregistration, indie zine feel, limited palette |
| `ink-wash` | 浓淡变化、飞白 | 宣纸渗透感、墨韵 | 层次感靠浓淡干湿 | Chinese ink wash sumi-e, rice paper texture, bold-thin brush contrast, elegant emptiness, zen atmosphere, poetic negative space |
| `poster-art` | 粗犷模板切割、强对比 | 半色调网点、统一填色 | 扁平、强视觉层级 | vintage propaganda poster, bold display typography, limited flat colors, strong visual hierarchy, political poster art, Swiss poster tradition |

---

## 参考图处理流程

当提供参考图时（老板给了风格参考、竞品封面等）：

### 流程

1. **保存参考图**：复制到 `refs/ref-NN-{slug}.{ext}`
2. **深度分析**：提取具体、可复现的元素（不是“有个 logo”，而是“logo 用平行竖线拼 m”）
3. **分类用途**：
   - `direct`：参考图直接传给模型 `--ref`（需要复现人物/核心元素时）
   - `style`：只提取视觉风格（线条、纹理、构图）
   - `palette`：只提取配色方案（hex 色值）
4. **写入 prompt**：用 MUST/REQUIRED 前缀强制约束，不能只传 `--ref` 不写文字描述（模型经常忽略 ref 图片）

### 深度分析提取清单

| 分析维度 | 好的描述 | 差的描述 |
|----------|---------|----------|
| 配色 | “#2D4A3E 深青 + #F5F0E0 米白” | “有深色和浅色” |
| 线条 | “2px 均匀线条，圆角端点” | “有线条” |
| 布局 | “底部 30% 暗色横幅放品牌” | “有个横幅” |
| 字体 | “大写、宽字距、无衬线” | “有文字” |

### 优先级规则

- 参考图 **覆盖默认**：如果参考图风格与预设配色/渲染冲突，参考图优先
- 具体 > 模糊：提取具体元素，不要“干净风格”这种模糊描述
- 生成后检查：确认参考元素在产出中可见，不可见则加强 prompt 重试

---

## 兼容矩阵

### Type × Rendering

| Type \ Rendering | 3d-icon | flat-vector | hand-drawn | painterly | digital | screen-print | chalk | oil-painting | ukiyo-e | collage | risograph | ink-wash | poster-art |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `hero` | ✓✓ | ✓ | ✓ | ✓ | ✓✓ | ✓ | ✗ | ✓✓ | ✓ | ✓ | ✗ | ✗ | ✓ |
| `conceptual` | ✓✓ | ✓✓ | ✗ | ✗ | ✓✓ | ✓ | ✓ | ✗ | ✗ | ✓ | ✓ | ✓✓ | ✓ |
| `typography` | ✓ | ✓✓ | ✓ | ✗ | ✓ | ✓✓ | ✓✓ | ✗ | ✗ | ✓ | ✓✓ | ✓ | ✓✓ |
| `metaphor` | ✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✓✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✓✓ | ✓ |
| `split` | ✓✓ | ✓✓ | ✓ | ✗ | ✓✓ | ✓ | ✗ | ✗ | ✓ | ✓✓ | ✓ | ✗ | ✓ |
| `minimal` | ✓ | ✓✓ | ✓ | ✓✓ | ✓ | ✓✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓✓ | ✓ |

### Type × Mood

| Type \ Mood | subtle | balanced | bold |
|---|:---:|:---:|:---:|
| `hero` | ✓ | ✓✓ | ✓✓ |
| `conceptual` | ✓✓ | ✓✓ | ✓ |
| `typography` | ✓ | ✓✓ | ✓✓ |
| `metaphor` | ✓✓ | ✓✓ | ✓ |
| `split` | ✓ | ✓✓ | ✓✓ |
| `minimal` | ✓✓ | ✓✓ | ✗ |

### Palette × Rendering

| Palette \ Rendering | 3d-icon | flat-vector | hand-drawn | painterly | digital | screen-print | chalk | oil-painting | ukiyo-e | collage | risograph | ink-wash | poster-art |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `tech-blue` | ✓✓ | ✓ | ✗ | ✗ | ✓✓ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ | ✗ | ✓ |
| `insight-blue` | ✓✓ | ✓✓ | ✗ | ✗ | ✓✓ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ | ✗ | ✓ |
| `action-orange` | ✓✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ | ✗ | ✓✓ |
| `solution-green` | ✓✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ | ✗ | ✗ |
| `trend-cyan` | ✓✓ | ✓✓ | ✗ | ✗ | ✓✓ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ | ✗ | ✓ |
| `mono` | ✓ | ✓✓ | ✓ | ✗ | ✓ | ✓✓ | ✓✓ | ✗ | ✓ | ✓✓ | ✓✓ | ✓ | ✓✓ |
| `warm` | ✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✗ | ✓✓ | ✓ | ✓ | ✓ | ✓ | ✗ |
| `dark` | ✓✓ | ✓ | ✗ | ✗ | ✓✓ | ✓✓ | ✓✓ | ✓ | ✗ | ✓ | ✓ | ✗ | ✓✓ |
| `gallery` | ✓ | ✓ | ✗ | ✓✓ | ✓ | ✓ | ✗ | ✓✓ | ✓ | ✓ | ✓ | ✓✓ | ✓ |
| `monet` | ✗ | ✗ | ✓ | ✓✓ | ✗ | ✗ | ✗ | ✓✓ | ✗ | ✓✓ | ✓ | ✗ | ✗ |
| `pop` | ✓ | ✓✓ | ✓ | ✗ | ✓ | ✓✓ | ✗ | ✗ | ✗ | ✓✓ | ✓✓ | ✗ | ✓✓ |
| `edo` | ✗ | ✓ | ✓ | ✓ | ✗ | ✓ | ✗ | ✓ | ✓✓ | ✗ | ✗ | ✓✓ | ✓ |
| `darkroom` | ✓ | ✗ | ✗ | ✓ | ✓✓ | ✓✓ | ✗ | ✓ | ✗ | ✓ | ✓ | ✗ | ✓ |

> ✓✓ 强推荐 | ✓ 可用 | ✗ 不推荐

### Type × Text

| Type \ Text | none | title-only | title-subtitle | text-rich |
|---|:---:|:---:|:---:|:---:|
| `hero` | ✓ | ✓✓ | ✓✓ | ✓ |
| `conceptual` | ✓✓ | ✓✓ | ✓ | ✓ |
| `typography` | ✗ | ✓ | ✓✓ | ✓✓ |
| `metaphor` | ✓✓ | ✓ | ✓ | ✗ |
| `split` | ✓ | ✓✓ | ✓ | ✓ |
| `minimal` | ✓✓ | ✓✓ | ✓ | ✗ |

### Font × Rendering

| Font \ Rendering | 3d-icon | flat-vector | hand-drawn | painterly | digital | screen-print | chalk | oil-painting | ukiyo-e | collage | risograph | ink-wash | poster-art |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `clean` | ✓✓ | ✓✓ | ✗ | ✗ | ✓✓ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ | ✗ | ✓ |
| `handwritten` | ✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✗ | ✓✓ | ✓ | ✓ | ✓✓ | ✗ | ✓✓ | ✗ |
| `serif` | ✓ | ✓ | ✗ | ✓ | ✓✓ | ✓ | ✗ | ✓✓ | ✓ | ✓ | ✓ | ✓✓ | ✓ |
| `display` | ✓✓ | ✓✓ | ✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✓ | ✓✓ | ✓✓ | ✗ | ✓✓ |

**兼容检查**：选定七维度后，检查上方矩阵中是否有 ✗ 组合。有则提示调整。另外检查 Art Reference 兼容矩阵（见上方 Art Reference 章节）。

---

## 内容信号自动推荐

**决策规则**（与小红书 presets.md 统一逻辑）：
1. 扫描文章关键词，匹配下表第一个命中行
2. 取推荐的六维度组合（或直接用预设快捷方式）
3. 用上方兼容矩阵校验组合无 ✗
4. 混合信号时取第一个匹配，不迭加多个维度推荐

公众号用「六维度」因为封面图是 AI 生图需要细粒度控制；小红书用「预设」因为预设已封装最佳组合。两套体系底层逻辑一致：内容信号 → 自动推荐 → 兼容校验 → 生成。

根据文章关键词自动推荐六维度组合：

| 文章关键词/类型 | Type | Palette | Rendering | Text | Mood |
|---------------|------|---------|-----------|------|------|
| AI、产品、工具、拆解、评测 | `hero` | `tech-blue` | `3d-icon` | title-only | balanced |
| 架构、框架、系统、分层、原理 | `conceptual` | `insight-blue` | `flat-vector` | title-only | subtle |
| 观点、趋势、判断、声明、预测 | `typography` | `mono` | `screen-print` | title-only | bold |
| 成长、转型、个人经历、反思 | `metaphor` | `warm` | `hand-drawn` | title-only | balanced |
| vs、对比、before/after、选型 | `split` | `tech-blue` | `3d-icon` | title-only | bold |
| 极简、核心、本质、一个概念 | `minimal` | `mono` | `flat-vector` | title-only | subtle |
| 效率、实战、工具实操 | `hero` | `action-orange` | `3d-icon` | title-subtitle | balanced |
| 行业、前沿、趋势报告 | `hero` | `trend-cyan` | `3d-icon` | title-only | balanced |
| 解决方案、破局、方法 | `hero` | `solution-green` | `3d-icon` | title-only | balanced |
| 电影感、高级、深度长文 | `typography` | `dark` | `screen-print` | title-only | bold |
| 哲学、本质、底层逻辑、第一性 | `minimal` | `edo` | `ink-wash` | title-only | subtle |
| 认知革命、范式转换、颠覆 | `hero` | `gallery` | `oil-painting` | title-only | bold |
| 争议、反直觉、打脸、不同意 | `typography` | `pop` | `risograph` | title-only | bold |
| 跨界、融合、碰撞、多视角 | `split` | `monet` | `collage` | title-only | balanced |
| 个人经历、深夜、独处、夜晚、回忆 | `hero` | `darkroom` | `digital` | title-only | balanced |
| 宣言、呼吁、必须、不得不 | `typography` | `pop` | `poster-art` | title-only | bold |
| 趋势、浪潮、变革、时代、洪流 | `hero` | `monet` | `oil-painting` | title-only | bold |
| 极简、克制、删繁就简、少即是多 | `minimal` | `gallery` | `ink-wash` | title-only | subtle |
| 文化、艺术、美学、品味 | `hero` | `gallery` | `oil-painting` | title-only | balanced |

---

## 预设快捷方式

常用组合一键选择：

| 预设名 | Type | Palette | Rendering | Font | 典型文章 |
|--------|------|---------|-----------|------|---------|
| `ai-product` | hero | tech-blue | 3d-icon | clean | AI产品拆解（**最常用**） |
| `methodology` | conceptual | insight-blue | flat-vector | clean | 方法论/框架文 |
| `bold-opinion` | typography | dark | screen-print | display | 观点输出/声明（mood=bold） |
| `pm-growth` | metaphor | warm | hand-drawn | handwritten | 个人成长/转型 |
| `versus` | split | tech-blue | 3d-icon | clean | 对比类文章 |
| `zen-core` | minimal | mono | flat-vector | serif | 极简深度文（mood=subtle） |
| `efficiency` | hero | action-orange | 3d-icon | clean | 效率/实战 |
| `trend-report` | hero | trend-cyan | digital | clean | 行业观察/数据 |
| `chalkboard` | conceptual | dark | chalk | handwritten | 教程/解释概念 |
| `watercolor` | metaphor | warm | painterly | serif | 文学/艺术/反思 |
| `cinematic` | hero | dark | screen-print | display | 电影感深度解读（mood=bold） |
| `dashboard` | conceptual | insight-blue | digital | clean | 数据分析/SaaS拆解 |
| `gallery-depth` | hero | gallery | oil-painting | serif | 深度分析/文化品味（Art Ref: monet-garden, Layout=full-bleed） |
| `eastern-zen` | minimal | edo | ink-wash | serif | 方法论本质/极简哲理（Art Ref: song-dynasty, Layout=centered） |
| `pop-challenge` | typography | pop | risograph | display | 争议观点/打破认知（Art Ref: warhol, Layout=centered, mood=bold） |
| `collage-mix` | split | monet | collage | clean | 跨界融合/多视角对比（Layout=split） |
| `film-story` | hero | darkroom | digital | serif | 个人经历/深度叙事（Art Ref: film-noir, Layout=full-bleed） |
| `poster-manifesto` | typography | pop | poster-art | display | 宣言/呼吁/强观点（Art Ref: bauhaus, Layout=centered, mood=bold） |

Text 默认 `title-only`，Mood 默认 `balanced`，除非预设标注（如 bold-opinion/cinematic → bold，zen-core → subtle）。

> ℹ️ 融合自 baoyu-cover-image v1.56.1 五维度体系 + Style Presets，适配公众号封面场景。

---

## 尺寸规范

| 用途 | 比例 | 生成尺寸 | 后处理 | 安全区 |
|------|------|---------|--------|--------|
| 公众号头条封面 | 2.35:1 | `2560x1440`(16:9) | `sips -c 1090 2560` 裁剪 | 中心 1090×1090 |
| 公众号分享卡片 | 1:1 | `1920x1920` | 无 | 全图 |
| 公众号次条 | 1:1 | `800x800` | 无 | 全图 |
| 小红书封面 | 3:4 | `1680x2240` | 无 | - |

### 生成与裁剪流程

```bash
# 1. AI 生图（16:9 高分辨率）
<WORKSPACE>/scripts/generate-image.sh --prompt "...组装好的prompt..." --filename cover.jpg --size 2560x1440

# 2. 裁剪为 2.35:1
sips -c 1090 2560 cover.jpg

# 3. 安全区验证：视觉检查中心 1090×1090 区域核心信息是否完整
# 4. 缩略图测试：缩放到 200px 宽查看标题是否可辨认
```

### 布局策略与安全区的关系

| Layout | 背景视觉 | 标题文字 | 安全区外 |
|--------|---------|---------|----------|
| `centered` | 纯色/渐变/轻纹理 | 安全区内居中 | 纯装饰或留白 |
| `full-bleed` | 铺满全图（名画/油画/光影） | 安全区内 + 遮罩保证可读 | 视觉延伸 |
| `split` | 左右分区 | 标题在中间偏左（安全区内） | 右侧视觉可被裁 |

---

## Prompt 组装

### 步骤

1. **选定五维度**（自动推荐或手动选择）
2. **兼容矩阵校验**（检查 3 张矩阵无 ✗）
3. **存 prompt 文件**：`prompts/00-cover.md`（⛔ 先存后生）
4. **生成图片**
5. **裁剪**（如需 2.35:1）

### Prompt 模板

```markdown
---
type: [hero/conceptual/typography/metaphor/split/minimal]
palette: [配色名]
rendering: [渲染名]
text: [none/title-only/title-subtitle]
mood: [subtle/balanced/bold]
---

[渲染风格的 Prompt 关键词，从维度3表格中复制]

配色：[配色色值，从维度2表格中复制]

构图：[构图方式描述，从维度1表格中复制]

内容：
- 标题：「[中文标题]」
- 副标题：「[副标题，如有]」
- 视觉元素：[与文章主题相关的具象物体/抽象图形]

约束：
- 中文文字清晰可读
- 文字和视觉不重叠
- 不要 emoji
- 横版，高质量
```

### 生图调用

```bash
# 首选：idealab Chat API（团队AK免费）
<WORKSPACE>/scripts/generate-image.sh "[组装好的 prompt]" cover.jpg

# 降级：Seedream（idealab 不可用时）
<WORKSPACE>/scripts/seedream-generate.sh \
  "[组装好的 prompt]" \
  cover.jpg "2560x1440" 1

# 裁剪为 2.35:1
sips -c 1090 2560 cover.jpg
```

---

## 多方案选择

每次封面图出 **2-3 个方案**供老板选择：

```markdown
## 方案 A（推荐）
- 预设：ai-product（hero + tech-blue + 3d-icon）
- 视觉：[具体视觉元素描述]

## 方案 B
- 预设：bold-opinion（typography + dark + screen-print）
- 视觉：[具体视觉元素描述]

## 方案 C（可选）
- 预设：methodology（conceptual + insight-blue + flat-vector）
- 视觉：[具体视觉元素描述]
```

方案之间必须在 **Type 或 Rendering** 上有明显差异（不只是换配色）。

---

## 生图工具优先级

1. **idealab Chat API**（首选）：`<WORKSPACE>/scripts/generate-image.sh`，团队AK免费无额度压力，~25s/张
2. **Seedream 5.0 Lite**（降级）：`<WORKSPACE>/scripts/seedream-generate.sh`，0.22元/张，idealab不可用时
3. **DashScope qwen-image-2.0-pro**（中文文字专用）：当中文渲染失败时
4. **HTML 截图**（兜底）：typography 类型封面可用 HTML 精确控制文字

---

## 内容结构图（可选）

放在文章开头、封面图之后，帮读者一图看全文。

### 风格

Graphic Recording / Visual Thinking 手绘风格：
- 白纸背景，无横线
- 黑色细线笔轮廓 + 彩色标记（青色、橙色、柔和红色）
- 放射状布局，箭头连接
- 16:9 比例

### Prompt 模板

```
Create a hand-drawn sketch visual summary about [文章主题].
Clean white paper background, no lines.
Art style: graphic recording / visual thinking.
Black fine-tip pen for outlines and text.
Colored markers (cyan, orange, soft red) for emphasis.
Main title "[文章标题]" centered in a 3D rectangular box.
Surround with radially distributed simple doodles, icons, and diagrams:
- [要点1]
- [要点2]
- [要点3]
Connect ideas with arrows. Clear hand-written block letters.
Layout 16:9, high quality.
```

### 决策规则

- 文章 ≥ 3 个主要观点：建议生成
- 文章内容简单或时间紧迫：可跳过

---

## 质量检查

### 尺寸与安全区
- [ ] 最终输出 2560×1090（2.35:1）
- [ ] 标题文字在中心 1090×1090 安全区内
- [ ] 左右装饰区无关键信息
- [ ] 缩放到 200px 宽，标题仍可辨认

### 文字与可读性
- [ ] 中文标题清晰，无重叠/模糊
- [ ] 文字区域有足够对比度（遮罩/纯色底）
- [ ] 字号在安全区内占比 ≥ 30%（不能太小）
- [ ] 无 emoji

### 维度与风格
- [ ] 七维度组合通过兼容矩阵检查
- [ ] Art Reference（如有）视觉锚点识别清晰
- [ ] Layout 与 Type 的绑定关系正确
- [ ] 主题契合文章内容
- [ ] 配色不超过 3-4 种主色
- [ ] 颜色鲜明，吸引眼球

### 文件
- [ ] Prompt 已保存到 `prompts/00-cover.md`
- [ ] 已去水印（AI 生图）
- [ ] 裁剪后比例正确（2.35:1）
