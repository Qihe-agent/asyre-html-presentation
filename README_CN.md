<div align="center">

# Asyre Presentation

**几分钟内为客户交付专业展示页，不是几小时。**

![License](https://img.shields.io/badge/License-MIT-blue)
![Styles](https://img.shields.io/badge/Styles-53%2B-brightgreen)
![Zero Deps](https://img.shields.io/badge/Dependencies-Zero-orange)
![Bilingual](https://img.shields.io/badge/Languages-EN%20%7C%20%E4%B8%AD%E6%96%87-blueviolet)

[**English**](README.md)

</div>

<br>

## 我们要解决的问题

你需要给客户展示一个方案 —— 产品介绍、策略汇报、项目 showcase。打开 PPT，跟模板较劲，导出 PDF，发邮件。客户在手机上打开 —— 排版全乱了。

或者你花 3 小时手写一个漂亮的 HTML 页面。效果惊艳，但下一个客户要完全不同的风格。从头再来。

**Asyre Presentation 解决这个问题。** 描述你的内容，选一个视觉风格，得到一个可直接交付的 HTML 展示页 —— 单文件、零依赖、任何设备都能打开。

## 你会得到什么

<!-- TODO: 截图 — 一个完整的展示页在浏览器中打开，显示封面页 + 暗色氛围底图 -->
<!-- ![Demo](assets/screenshots/demo-full.png) -->

一个 `.html` 文件，它能：
- 在任何浏览器、任何设备上打开
- 看起来像专业设计公司做的
- 自带键盘导航、流畅动画、响应式缩放
- 一条命令部署到 URL，或者直接当文件发送

## 实际效果

### 客户方案展示

<!-- TODO: 截图 — Bold Signal 风格的 pitch deck，展示封面 + 一页内容页并排 -->
<!-- ![Pitch Deck](assets/screenshots/usecase-pitch.png) -->

一个创业团队需要向投资人展示他们的 AI 产品。用 **Bold Signal** 风格，8 分钟生成。深色背景、自信的排版、数据驱动的统计页面。部署到 Vercel URL，会议中直接打开分享。

### 产品 Showcase 页面

<!-- TODO: 截图 — Keynote Noir 风格的产品展示，带 AI 背景图的产品特性页 -->
<!-- ![Product Showcase](assets/screenshots/usecase-product.png) -->

一个电商品牌需要为零售合作伙伴做新品系列的视觉展示。12 页幻灯片，每页都有 AI 生成的氛围底图，匹配品牌调性。交付为单个 HTML 文件 —— 合作伙伴直接在平板上打开浏览。

### 培训 / 工作坊演示

<!-- TODO: 截图 — Campus White 风格的教学 deck，展示一个步骤教程页 -->
<!-- ![Training](assets/screenshots/usecase-training.png) -->

一家咨询公司为企业客户做 AI 落地工作坊。每次工作坊都需要定制化的演示文稿。用 Asyre Presentation，每个客户的 deck 15 分钟内搞定 —— 通过 `.impeccable.md` 匹配客户的品牌色彩。

### 演讲 / 分享

<!-- TODO: 截图 — Cinema Scope 风格的演讲 deck，全幅深色页面 + 戏剧感排版 -->
<!-- ![Conference](assets/screenshots/usecase-conference.png) -->

一位演讲者准备了一场 20 页的 AI 原生商业演讲。每页都有独特的 Gemini 生成背景图 —— 电锯、镜子、锻造、利刃 —— 作为每个章节的视觉隐喻。观众在演讲结束后很久还记得那些画面。

> 查看 `examples/backgrounds/` 目录，里面有这些演讲中实际使用的 AI 生成图片。

## 工作流程

### 1. 描述你的内容

告诉 AI 你的展示页是关于什么的 —— 主题、受众、核心要点。可以贴笔记、传 Markdown 文件，甚至导入一个 PowerPoint 转换。

### 2. 选择视觉风格

53+ 精选风格，横跨 7 大类别。浏览画廊，让 AI 根据情绪推荐，或者从你的品牌设计上下文生成一个全新的自定义风格。

<!-- TODO: 截图 — 风格画廊，6 个风格缩略图网格（2 暗色、2 亮色、1 编辑风、1 大胆风） -->
<!-- ![Style Gallery](assets/screenshots/style-gallery.png) -->

| 类别 | 代表风格 | 适用场景 |
|------|---------|---------|
| 暗色 | Keynote Noir, Bold Signal, Neon Cyber | 产品发布、大会演讲 |
| 亮色 | Swiss Modern, Paper & Ink, Pastel Geometry | 商务会议、教学培训 |
| 编辑风 | Editorial Serif, Fashion Editorial | 思想领导力、奢侈品牌 |
| 大胆创意 | Electric Studio, Pop Art, Neon Brutalism | 创业路演、创意推介 |
| 复古 | Art Deco Gatsby, Risograph, Vintage Poster | 风格化展示 |
| 艺术 | Surrealism Gallery, Soft Dreamy | 艺术设计、作品集 |
| 文化特色 | 东方墨韵, 和風, Blueprint, Bauhaus | 文化活动、主题展示 |

### 3. AI 氛围底图（可选）

每一页都可以有独特的 AI 生成氛围背景 —— 抽象的视觉隐喻，增加层次感但不干扰内容阅读。

<!-- TODO: 截图 — 同一页内容的前后对比：纯 CSS 背景 vs 加了 AI 底图的效果 -->
<!-- ![Background Comparison](assets/screenshots/bg-comparison.png) -->

**透明度和遮罩根据页面类型精细调节：**

| 页面类型 | 图片可见度 | 目的 |
|---------|-----------|------|
| 封面 | 25-35% | 定调 |
| 内容页 | 8-12% | 微妙氛围 |
| 章节分隔 | 20-30% | 视觉节奏 |
| 结尾页 | 25-35% | 情感收束 |

### 4. 获得你的展示页

一个 HTML 文件，可以：
- **本地打开** —— 双击即可演示
- **部署到 URL** —— `npx vercel --prod` 生成分享链接
- **导出 PDF** —— 用于离线分享
- **浏览器内编辑** —— 支持最后一刻的文字修改

## 三级定制深度

<!-- TODO: 截图 — 同一内容的 3 页并排展示：Level 0（纯预设）、Level 1（提升预设）、Level 2（自定义风格） -->
<!-- ![Three Levels](assets/screenshots/three-levels.png) -->

| 级别 | 做什么 | 速度 |
|------|-------|------|
| **Level 0: 纯预设** | 从 53 个风格中选一个，直接生成 | 最快（~5 分钟） |
| **Level 1: 预设提升** | 预设 + 通过 `.impeccable.md` 品牌化微调字体/配色/动效 | 快（~8 分钟） |
| **Level 2: 自定义风格** | AI 从你的品牌上下文合成全新的视觉体系 | 中等（~15 分钟） |

每个级别都可以叠加 AI 背景图。

## 安装

### Claude Code

```bash
git clone https://github.com/yzha0302/asyre-html-presentation ~/.claude/skills/asyre-presentation
```

使用：
```
/asyre-presentation
```

### OpenClaw

```bash
clawhub install asyre-presentation
```

### 其他 AI 工具

将 `SKILL.md` 作为 system prompt，引用支持文件即可。

## 示例底图

`examples/backgrounds/` 目录包含真实演讲中使用的 AI 生成图片：

**`taming-the-blade/`** — AI 哲学演讲的视觉隐喻系列：

<!-- TODO: 4 张 taming-the-blade 图片网格：01-chainsaw.png, 03-control.png, 05-mirror.png, 08-trust.png -->
<!-- ![Taming the Blade](assets/screenshots/examples-blade.png) -->

| 图片 | 隐喻 |
|------|------|
| `01-chainsaw` | 原始力量 — AI 如同未驯服的电锯 |
| `02-perception` | 我们如何看待 AI |
| `03-control` | 掌握控制权 |
| `05-mirror` | AI 映射创造者 |
| `06-memory` | AI 记住了什么 |
| `08-trust` | 建立与 AI 的信任 |
| `10-eternal` | 长期博弈 |

**`ai-native-business/`** — AI 原生商业策略演讲：

<!-- TODO: 4 张 ai-native-business 图片网格：s01-title.jpg, s04-replace.png, s08-forge.png, s12-blade.png -->
<!-- ![AI Native Business](assets/screenshots/examples-business.png) -->

这些图片展示了底图的设计思路：**抽象、有氛围感、暗色调**，每页承载独特的视觉隐喻。当你在 Phase 2.8 中选择"每页都生成"时，AI 会生成类似风格的背景图。

## 文件结构

```
asyre-html-presentation/
├── SKILL.md                  # 核心工作流（AI 读取这个文件）
├── DESIGN_ELEVATION.md       # 品牌上下文如何提升设计
├── STYLE_PRESETS.md          # 53 个风格定义（含 CSS 变量）
├── html-template.md          # HTML/JS 架构 + 11 种幻灯片类型
├── animation-patterns.md     # 按情绪分类的动画参考
├── SCENARIO_TEMPLATES.md     # 叙事结构（路演、发布、演讲、教学、作品集）
├── viewport-base.css         # 强制响应式 CSS
├── style-gallery.html        # 风格浏览器
├── styles/                   # 43 个风格参考实现
├── scenarios/                # 114 个完整示例演示
├── examples/backgrounds/     # 实战 AI 生成底图
└── scripts/extract-pptx.py   # PowerPoint 提取工具
```

## 致谢

- **[Next Slide](https://github.com/codesstar/next-slide)** by Callum — 核心演示引擎
- **Impeccable Design System** — 设计哲学与反 AI Slop 质量体系

## License

MIT License. 详见 [LICENSE](LICENSE)。

---

<div align="center">

**别再做幻灯片了。做让人记住的东西。**

![Asyre](https://img.shields.io/badge/Asyre-Presentation-black?style=for-the-badge)

Powered by [**Asyre**](https://github.com/yzha0302)

</div>
