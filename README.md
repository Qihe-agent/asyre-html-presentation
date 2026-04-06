<div align="center">

# Asyre Presentation

> *"你的下个 ppt，何必是 PPT"*

![License](https://img.shields.io/badge/License-MIT-blue)
![Styles](https://img.shields.io/badge/Styles-53%2B-brightgreen)
![Zero Deps](https://img.shields.io/badge/Dependencies-Zero-orange)
![Bilingual](https://img.shields.io/badge/Bilingual-EN%20%7C%20%E4%B8%AD%E6%96%87-blueviolet)

<br>

**还在用 PowerPoint 做演示稿？** → 单个 HTML 文件，零依赖，随处打开

**AI 生成的幻灯片千篇一律？** → Impeccable 设计体系反 AI slop，每份独一无二

**纯 CSS 背景太单调？** → 每页可选 AI 生成氛围底图

<br>

### HTML 演示文稿引擎，融合 Impeccable 设计体系 + AI 背景图生成

<br>

[**快速开始**](#快速开始) · [**核心能力**](#核心能力) · [**风格库**](#风格库) · [**工作流程**](#工作流程)

</div>

<br>

---

## 核心能力

| 能力 | 详情 |
|------|------|
| **53+ 预设风格** | 7 大类别：暗色、亮色、编辑、大胆、复古、艺术、文化 |
| **Impeccable 设计提升** | 读取 `.impeccable.md` 设计上下文，突破模板限制，生成品牌化自定义风格 |
| **AI 背景图** | 每页可选 Gemini/Imagen 生成氛围底图，暗色调 + 主题隐喻 |
| **零依赖** | 单个 HTML 文件，内联 CSS/JS，随处打开 |
| **中英双语** | 完整 CJK 字体支持，自动行高调整 |
| **PPT/Markdown 转换** | 导入 .pptx 或 .md 文件，自动转为 HTML 演示文稿 |
| **反 AI Slop** | 内置 AI Slop 检测，拒绝千篇一律的生成结果 |
| **响应式** | 所有值使用 `clamp()`，手机到4K 屏幕自适应 |
| **一键部署** | Vercel 部署 + PDF 导出 |

## 三层视觉体系

```
Layer 1: CSS 预设/自定义（每页都有）     ← 53 个精心设计的风格预设
Layer 2: Impeccable 设计提升（每页都有） ← 品牌化字体/配色/动效微调
Layer 3: AI 背景图（可选）              ← 每页独立的氛围底图
```

## 风格库

| 类别 | 风格 | 适用场景 |
|------|------|----------|
| 暗色主题 | Keynote Noir, Bold Signal, Neon Cyber, Terminal Green 等 11 个 | 会议、产品发布、技术演讲 |
| 亮色主题 | Swiss Modern, Paper & Ink, Pastel Geometry 等 11 个 | 学术、商务、教学 |
| 编辑风 | Editorial Serif, Fashion Editorial 等 4 个 | 杂志风、思想领导力 |
| 大胆创意 | Electric Studio, Pop Art, Neon Brutalism 等 7 个 | 创业、创意推介 |
| 复古 | Art Deco Gatsby, Risograph, Vintage Poster 等 5 个 | 怀旧、风格化 |
| 艺术 | Surrealism Gallery, Scrapbook, Soft Dreamy 等 7 个 | 艺术、设计、作品集 |
| 文化特色 | 东方墨韵, 和風, Blueprint, Bauhaus 等 8 个 | 文化活动、主题演示 |

## 工作流程

```
检测模式 → 内容采集 → [设计上下文] → 风格选择 → [AI 背景图] → 生成 HTML → QA → 交付
                          可选                    可选          ↓
                                                          部署 / PDF 导出
```

**三级创意自由度：**
- **Level 0**: 纯预设 — 53 个风格直接用，最快
- **Level 1**: 预设提升 — 有 `.impeccable.md` 时，自动微调字体/配色/动效
- **Level 2**: 自定义风格 — 从设计上下文合成全新视觉体系

## 快速开始

### Claude Code

```bash
# 安装技能
git clone https://github.com/yzha0302/asyre-html-presentation ~/.claude/skills/asyre-presentation

# 使用
/asyre-presentation
```

### OpenClaw

```bash
clawhub install asyre-presentation
```

### 其他 AI 工具

将 `SKILL.md` 作为 system prompt，并引用支持文件。

## 文件结构

```
asyre-html-presentation/
├── SKILL.md                ← 技能主文档（工作流程指令）
├── DESIGN_ELEVATION.md     ← Impeccable 设计提升协议
├── STYLE_PRESETS.md        ← 53 个预设风格完整定义
├── html-template.md        ← HTML/JS 架构 + 11 种幻灯片类型
├── animation-patterns.md   ← 9 种情绪的动画参考
├── SCENARIO_TEMPLATES.md   ← 5 种场景叙事结构
├── viewport-base.css       ← 强制响应式 CSS
├── style-gallery.html      ← 风格浏览器
├── styles/                 ← 43 个风格参考实现
├── scenarios/              ← 114 个完整示例演示
└── scripts/
    └── extract-pptx.py     ← PowerPoint 提取工具
```

## 致谢

- **Next Slide** by [Callum](https://github.com/codesstar/next-slide) — 核心演示文稿引擎
- **Impeccable Design System** — 设计哲学与反 AI Slop 体系

## License

MIT License. See [LICENSE](LICENSE) for details.

---

<div align="center">

**你的下个演示文稿，不需要 PowerPoint。**

![Asyre](https://img.shields.io/badge/Asyre-Presentation-black?style=for-the-badge)

Powered by [**Asyre**](https://github.com/yzha0302)

</div>
