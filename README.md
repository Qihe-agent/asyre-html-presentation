<div align="center">

# Asyre Presentation

**Create client-ready presentation pages in minutes, not hours.**

![License](https://img.shields.io/badge/License-MIT-blue)
![Styles](https://img.shields.io/badge/Styles-53%2B-brightgreen)
![Zero Deps](https://img.shields.io/badge/Dependencies-Zero-orange)
![Bilingual](https://img.shields.io/badge/Languages-EN%20%7C%20%E4%B8%AD%E6%96%87-blueviolet)

[**中文版**](README_CN.md)

</div>

<br>

## The Problem

You need to present ideas to a client — a product pitch, a strategy deck, a project showcase. You open PowerPoint, fight with templates, export a PDF, and email it. The client opens it on their phone — it looks terrible.

Or you spend 3 hours hand-coding a beautiful HTML page. It looks amazing, but the next client needs a completely different style. Start over.

**Asyre Presentation solves this.** Describe what you want, pick a visual style, and get a production-ready HTML presentation page — single file, zero dependencies, works everywhere.

## What You Get

<!-- TODO: Screenshot — a full presentation page open in browser, showing the cover slide with dark atmospheric background -->
<!-- ![Demo](assets/screenshots/demo-full.png) -->

A single `.html` file that:
- Opens in any browser, on any device
- Looks like a professional agency built it
- Includes keyboard navigation, smooth animations, and responsive scaling
- Can be deployed to a URL in one command, or sent as a file

## Real Results

### Client Pitch Deck

<!-- TODO: Screenshot — pitch deck example with Bold Signal style, showing cover + one content slide side by side -->
<!-- ![Pitch Deck](assets/screenshots/usecase-pitch.png) -->

A startup needed to present their AI product to investors. Generated in 8 minutes with the **Bold Signal** style. Dark background, confident typography, data-driven stats slides. Deployed to a Vercel URL and shared in the meeting.

### Product Showcase Page

<!-- TODO: Screenshot — product showcase with Keynote Noir style, showing product features with AI background images -->
<!-- ![Product Showcase](assets/screenshots/usecase-product.png) -->

An e-commerce brand needed a visual walkthrough of their new product line for a retail partner meeting. 12 slides with AI-generated atmospheric backgrounds matching the brand's aesthetic. Delivered as a single HTML file — the partner opened it directly on their tablet.

### Training & Workshop Deck

<!-- TODO: Screenshot — teaching deck with Campus White style, showing a step-by-step tutorial slide -->
<!-- ![Training](assets/screenshots/usecase-training.png) -->

A consulting firm runs AI adoption workshops for enterprise clients. Each workshop needs a customized deck. With Asyre Presentation, they generate a new deck for each client in under 15 minutes — matching the client's brand colors via `.impeccable.md`.

### Conference Talk

<!-- TODO: Screenshot — conference talk with Cinema Scope style, showing a full-bleed dark slide with dramatic typography -->
<!-- ![Conference](assets/screenshots/usecase-conference.png) -->

A speaker prepared a 20-slide talk on AI-native business. Each slide has a unique Gemini-generated background image — chainsaw, mirror, forge, blade — as visual metaphors for each section. The audience remembers the visuals long after the talk.

> See `examples/backgrounds/` for the actual AI-generated images used in these presentations.

## How It Works

### 1. Describe Your Content

Tell the AI what your presentation is about — topic, audience, key points. Paste your notes, a markdown file, or even a PowerPoint to convert.

### 2. Choose a Visual Style

53+ curated styles across 7 categories. Browse the gallery, let the AI recommend based on mood, or generate a fully custom style from your brand's design context.

<!-- TODO: Screenshot — style gallery showing 6 style thumbnails in a grid (2 dark, 2 light, 1 editorial, 1 bold) -->
<!-- ![Style Gallery](assets/screenshots/style-gallery.png) -->

| Category | Examples | Best For |
|----------|----------|----------|
| Dark | Keynote Noir, Bold Signal, Neon Cyber | Product launches, conferences |
| Light | Swiss Modern, Paper & Ink, Pastel Geometry | Business meetings, teaching |
| Editorial | Editorial Serif, Fashion Editorial | Thought leadership, luxury brands |
| Bold | Electric Studio, Pop Art, Neon Brutalism | Startups, creative pitches |
| Retro | Art Deco Gatsby, Risograph, Vintage Poster | Stylized presentations |
| Artistic | Surrealism Gallery, Soft Dreamy | Art, design, portfolios |
| Cultural | 东方墨韵, 和風, Blueprint, Bauhaus | Cultural events, themed decks |

### 3. Add AI Background Images (Optional)

Each slide can have a unique AI-generated atmospheric background — abstract visual metaphors that add depth without distracting from the content.

<!-- TODO: Screenshot — before/after comparison: same slide with pure CSS background vs. with AI-generated atmospheric image behind it -->
<!-- ![Background Comparison](assets/screenshots/bg-comparison.png) -->

**Opacity and overlay are tuned per slide type:**

| Slide Type | Image Visibility | Purpose |
|-----------|-----------------|---------|
| Cover | 25-35% | Set the mood |
| Content | 8-12% | Subtle atmosphere |
| Section Break | 20-30% | Visual punctuation |
| Closing | 25-35% | Emotional impact |

### 4. Get Your Presentation

A single HTML file, ready to:
- **Open locally** — double-click to present
- **Deploy to a URL** — `npx vercel --prod` for a shareable link
- **Export to PDF** — for offline sharing
- **Edit in browser** — inline editing support for last-minute changes

## Three Levels of Customization

<!-- TODO: Screenshot — 3 slides side by side showing the same content in Level 0 (pure preset), Level 1 (elevated preset), Level 2 (custom from design context) -->
<!-- ![Three Levels](assets/screenshots/three-levels.png) -->

| Level | What It Does | Speed |
|-------|-------------|-------|
| **Level 0: Pure Preset** | Pick from 53 styles, generate immediately | Fastest (~5 min) |
| **Level 1: Elevated Preset** | Preset + brand-aware font/color/animation tweaks via `.impeccable.md` | Fast (~8 min) |
| **Level 2: Custom Style** | AI synthesizes a completely new visual system from your brand context | Medium (~15 min) |

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

<!-- TODO: Grid of 4 images from taming-the-blade: 01-chainsaw.png, 03-control.png, 05-mirror.png, 08-trust.png -->
<!-- ![Taming the Blade](assets/screenshots/examples-blade.png) -->

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

<!-- TODO: Grid of 4 images from ai-native-business: s01-title.jpg, s04-replace.png, s08-forge.png, s12-blade.png -->
<!-- ![AI Native Business](assets/screenshots/examples-business.png) -->

These images demonstrate the approach: **abstract, atmospheric, dark-toned**, with each slide carrying a unique visual metaphor. The AI generates similar backgrounds when you choose "Every slide" in Phase 2.8.

## File Structure

```
asyre-html-presentation/
├── SKILL.md                  # Core workflow (the AI reads this)
├── DESIGN_ELEVATION.md       # How brand context elevates designs
├── STYLE_PRESETS.md          # 53 style definitions with CSS variables
├── html-template.md          # HTML/JS architecture, 11 slide types
├── animation-patterns.md     # Animation reference by mood
├── SCENARIO_TEMPLATES.md     # Narrative structures (pitch, launch, talk, teach, portfolio)
├── viewport-base.css         # Mandatory responsive CSS
├── style-gallery.html        # Visual style browser
├── styles/                   # 43 reference implementations
├── scenarios/                # 114 complete example presentations
├── examples/backgrounds/     # Real AI-generated background images
└── scripts/extract-pptx.py   # PowerPoint extraction tool
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
