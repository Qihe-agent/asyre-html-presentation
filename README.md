<div align="center">

# Asyre Presentation

**Create client-ready presentation pages in minutes, not hours.**

![License](https://img.shields.io/badge/License-MIT-blue)
![Styles](https://img.shields.io/badge/Styles-53%2B-brightgreen)
![Zero Deps](https://img.shields.io/badge/Dependencies-Zero-orange)
![Bilingual](https://img.shields.io/badge/Languages-EN%20%7C%20%E4%B8%AD%E6%96%87-blueviolet)

[**中文版**](README_CN.md)

<br>

![Cover](assets/screenshots/cover-lobster.png)

</div>

<br>

## The Problem

You need to present ideas to a client — a product pitch, a strategy deck, a project showcase. You open PowerPoint, fight with templates, export a PDF, and email it. The client opens it on their phone — it looks terrible.

**Asyre Presentation solves this.** Describe what you want, pick a visual style, and get a production-ready HTML presentation page — single file, zero dependencies, works everywhere.

## What It Looks Like

Every slide combines AI-generated concept art backgrounds with precise typography and layout — the result feels like a keynote at a dark theater, not a template from a slide library.

**Cover slide — full-bleed AI background with editorial typography:**

![Cover](assets/screenshots/cover-lobster.png)

**Data visualization — clean layout on dark canvas:**

![Data](assets/screenshots/data-visualization.png)

**Content slides — each with a unique visual metaphor as background:**

| | |
|---|---|
| ![Chainsaw](assets/screenshots/slide-chainsaw.png) | ![Perception](assets/screenshots/slide-perception.png) |

*Left: "It's a chainsaw, not a knife" — raw power metaphor. Right: "Perception > Technical skill" — eye as metaphor for awareness.*

**Interaction and trust — atmospheric backgrounds that reinforce the message:**

![Trust](assets/screenshots/slide-trust.png)

*"Figure out what it's doing, then let go" — hands releasing a golden leash as trust metaphor.*

## How It Works

### 1. Describe Your Content

Tell the AI what your presentation is about — topic, audience, key points. Paste your notes, a markdown file, or even a PowerPoint to convert.

### 2. Choose a Visual Style

**Asyre Dark Gold** is the default — dark cinematic backgrounds, amber/gold accents, editorial serif typography. Or pick from 53+ other curated styles:

| Category | Examples | Best For |
|----------|----------|----------|
| **Asyre Dark Gold** | *Signature style* | Client pitches, keynotes, strategy |
| Dark | Keynote Noir, Bold Signal, Neon Cyber | Product launches, conferences |
| Light | Swiss Modern, Paper & Ink, Pastel Geometry | Business meetings, teaching |
| Editorial | Editorial Serif, Fashion Editorial | Thought leadership, luxury brands |
| Bold | Electric Studio, Pop Art, Neon Brutalism | Startups, creative pitches |
| Retro | Art Deco Gatsby, Risograph | Stylized presentations |
| Artistic | Surrealism Gallery, Soft Dreamy | Art, design, portfolios |
| Cultural | 东方墨韵, 和風, Blueprint, Bauhaus | Cultural events, themed decks |

### 3. AI Background Images (Optional)

Each slide can have a unique AI-generated atmospheric background. Not literal illustrations — abstract visual metaphors that add depth.

The image generation follows a proven style system:
- **Always** pure black background with amber/gold tones
- **Always** concept art aesthetic, semi-transparent subjects
- **Each slide** gets a different metaphor (chainsaw = power, eye = perception, mirror = reflection, flame = long-term vision)
- **Never** photorealistic, never neon/cyan (anti AI-slop)

See `examples/backgrounds/` for real AI-generated images from actual presentations.

### 4. Get Your Presentation

A single HTML file. Open it locally, deploy to a URL with one command, or export to PDF.

## Three Levels of Customization

| Level | What It Does | Speed |
|-------|-------------|-------|
| **Level 0: Pure Preset** | Pick from 53+ styles, generate immediately | ~5 min |
| **Level 1: Elevated Preset** | Preset + brand-aware font/color tweaks via `.impeccable.md` | ~8 min |
| **Level 2: Custom Style** | AI synthesizes a new visual system from your brand context | ~15 min |

Every level can optionally add AI background images.

## Installation

### Claude Code

```bash
git clone https://github.com/yzha0302/asyre-html-presentation ~/.claude/skills/asyre-presentation
```

Then use it:
```
/asyre-presentation
```

### OpenClaw

```bash
clawhub install asyre-presentation
```

### Other AI Tools

Use `SKILL.md` as a system prompt and reference the supporting files.

## Example Backgrounds

The `examples/backgrounds/` directory contains AI-generated images from real presentations:

**`taming-the-blade/`** — Visual metaphors for an AI philosophy talk:

| Image | Metaphor |
|-------|----------|
| `01-chainsaw` | Raw power — AI as an uncontrolled tool |
| `02-perception` | How we see AI |
| `03-control` | Taking the reins |
| `05-mirror` | AI reflects its creator |
| `06-memory` | What AI remembers |
| `08-trust` | Building trust with AI |
| `10-eternal` | The long game |

**`ai-native-business/`** — Slides for an AI-native business strategy deck:

| Image | Metaphor |
|-------|----------|
| `s01-title` | Opening statement |
| `s02-cost` | The cost of not using AI |
| `s04-replace` | What AI replaces |
| `s08-forge` | Forging new capabilities |
| `s12-blade` | The sharpened edge |

## Live Examples

These presentations were built with Asyre Presentation and are live on our server:

- **驯服利刃 (Taming the Blade)** — http://13.228.189.206/taming-the-blade/
- **AI Native Business** — http://13.228.189.206/ai-native-business/

## File Structure

```
asyre-html-presentation/
├── SKILL.md                    # Core workflow (the AI reads this)
├── ASYRE_BRAND_PRESET.md       # Asyre Dark Gold style + image prompt system
├── DESIGN_ELEVATION.md         # How brand context elevates designs
├── STYLE_PRESETS.md            # 53 style definitions with CSS variables
├── html-template.md            # HTML/JS architecture, 11 slide types
├── animation-patterns.md       # Animation reference by mood
├── SCENARIO_TEMPLATES.md       # Narrative structures
├── viewport-base.css           # Mandatory responsive CSS
├── style-gallery.html          # Visual style browser
├── styles/                     # 43 reference implementations
├── scenarios/                  # 114 complete example presentations
├── examples/backgrounds/       # Real AI-generated background images
└── scripts/extract-pptx.py     # PowerPoint extraction tool
```

## Credits

- **[Next Slide](https://github.com/codesstar/next-slide)** by Callum — core presentation engine
- **Impeccable Design System** — design philosophy and anti-AI-slop quality gates

## License

MIT License. See [LICENSE](LICENSE).

---

<div align="center">

**Stop making slides. Start making impressions.**

![Asyre](https://img.shields.io/badge/Asyre-Presentation-black?style=for-the-badge)

Powered by [**Asyre**](https://github.com/yzha0302)

</div>
