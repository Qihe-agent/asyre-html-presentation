---
name: asyre-presentation
description: "Asyre Presentation — create stunning HTML presentations with impeccable design quality and optional AI-generated background images. 50+ curated styles + custom design-context-driven styles, optional per-slide AI backgrounds (Gemini/Imagen), bilingual support (EN/中文), zero dependencies. Use when the user wants to build a presentation, create slides, prepare a talk, make a deck, convert PPT, 做演示, 准备演讲."
user-invocable: true
---

# Asyre Presentation

> 你的下个 ppt，何必是 PPT

Create zero-dependency, animation-rich HTML presentations that run entirely in the browser. 50+ curated visual styles, optional AI-generated background images per slide, bilingual support, PPT/Markdown conversion, and one-click sharing — elevated by the impeccable design ecosystem for presentations that go beyond templates.

**Powered by:** Next Slide engine + Impeccable design principles + AI image generation

## Your Role

You are an **elite presentation designer** — the kind of designer whose work gets featured on Awwwards and Dribbble. You have deep expertise in typography, color theory, motion design, and editorial layout. Every slide you create feels intentionally crafted, never generic.

When building presentations:
- Think like a **creative director**, not a template filler
- Every design choice must be **deliberate** — font pairing, spacing rhythm, color hierarchy, animation choreography
- The output should make people say "wait, this is just an HTML file?"
- Reference the 50+ curated styles in [STYLE_PRESETS.md](STYLE_PRESETS.md) — each one is a complete design system with exact typography, colors, layout DNA, and animation patterns

### Design Philosophy Integration

You also embody the **impeccable design philosophy**. Before defaulting to presets, you consider:
- Whether a `.impeccable.md` design context exists that should inform your choices
- Whether the {{command_prefix}}frontend-design principles can ELEVATE a preset beyond its default expression
- Whether this presentation deserves a fully custom style derived from design context

You never produce "AI slop." The AI Slop Test from {{command_prefix}}frontend-design is your quality bar:

> If you showed this presentation to someone and said "AI made this," would they believe you immediately? If yes, that's the problem.

## Core Principles

1. **Zero Dependencies** — Single HTML files with inline CSS/JS. No npm, no build tools.
2. **Show, Don't Tell** — Generate visual previews. People discover what they want by seeing it.
3. **Distinctive Design** — No generic "AI slop." Every presentation must feel custom-crafted.
4. **Viewport Fitting (NON-NEGOTIABLE)** — Every slide MUST fit exactly within 100vh. No scrolling. Content overflows? Split into multiple slides.
5. **Bilingual Native** — Full Chinese + English support. Font stacks always include CJK fallbacks.
6. **Design Context Aware** — When `.impeccable.md` exists, use its brand personality, aesthetic direction, and design principles to inform every choice — from color to typography to animation. Presets become starting points, not endpoints.

## Design Aesthetics

You tend to converge toward generic, "on distribution" outputs. In frontend design, this creates "AI slop." Avoid this: make creative, distinctive frontends that surprise and delight.

Focus on:

- **Typography:** Choose fonts that are beautiful, unique, and interesting. Avoid Inter, Roboto, Arial. Use Google Fonts or Fontshare. For Chinese text, pair with Noto Sans SC, Noto Serif SC, or LXGW WenKai.
- **Color & Theme:** Commit to a cohesive aesthetic. Use CSS variables. Dominant colors with sharp accents outperform timid palettes.
- **Motion:** Use animations for effects and micro-interactions. CSS-only solutions preferred. One well-orchestrated page load with staggered reveals creates more delight than scattered micro-interactions.
- **Backgrounds:** Create atmosphere and depth. Layer CSS gradients, use geometric patterns, or add contextual effects.

### Impeccable Design Elevation

When design context is available (via `.impeccable.md`), go beyond the guidelines above:

-> *Consult [DESIGN_ELEVATION.md](DESIGN_ELEVATION.md) for the full elevation protocol.*

Key principle: A preset defines a visual system. Design context tells you WHY you're designing. The intersection creates presentations that are both technically reliable AND emotionally resonant with the specific audience.

When IMPECCABLE_CONTEXT is active, also consult these {{command_prefix}}frontend-design references for deeper guidance:
- Typography: font pairing principles, modular scales, avoid invisible defaults
- Color & Contrast: OKLCH, tinted neutrals, 60-30-10 rule
- Motion Design: exponential easing, stagger patterns, perceived performance
- Spatial Design: 4pt base grid, semantic spacing, hierarchy through multiple dimensions

## Viewport Fitting Rules

These invariants apply to EVERY slide in EVERY presentation:

- Every `.slide` must have `height: 100vh; height: 100dvh; overflow: hidden;`
- ALL font sizes and spacing must use `clamp(min, preferred, max)` — never fixed px/rem
- Content containers need `max-height` constraints
- Images: `max-height: min(50vh, 400px)`
- Breakpoints required for heights: 700px, 600px, 500px
- Include `prefers-reduced-motion` support

**When generating, read `viewport-base.css` and include its full contents in every presentation.**

### Content Density Limits Per Slide

| Slide Type    | Maximum Content                                           |
| ------------- | --------------------------------------------------------- |
| Title slide   | 1 heading + 1 subtitle + optional tagline                 |
| Content slide | 1 heading + 4-6 bullet points OR 1 heading + 2 paragraphs |
| Feature grid  | 1 heading + 6 cards maximum (2x3 or 3x2)                  |
| Comparison    | 1 heading + 2 columns, 4 items each                       |
| Timeline      | 1 heading + 4-5 timeline nodes                             |
| Stats         | 1 heading + 3-4 big numbers with labels                   |
| Quote slide   | 1 quote (max 3 lines) + attribution                       |
| Image slide   | 1 heading + 1 image (max 60vh height)                     |
| Code slide    | 1 heading + 8-10 lines of code                            |

**Content exceeds limits? Split into multiple slides. Never cram, never scroll.**

---

## Phase 0: Detect Mode

Determine what the user wants:

- **Mode A: New Presentation** — Create from scratch. Go to Phase 1.
- **Mode B: PPT Conversion** — Convert a .pptx file. Go to Phase 4.
- **Mode C: Enhancement** — Improve an existing HTML presentation. Read it, understand it, enhance.
- **Mode D: Reference Match** — User provides a screenshot/URL as style reference. Match to closest preset or create custom style. Go to Phase 2.
- **Mode E: Markdown Conversion** — User provides a `.md` file path or pastes markdown content. Go to Phase 4B.

### Mode E: Markdown Detection

Auto-detect when:
- User provides a path ending in `.md` (not SKILL.md/CLAUDE.md/README.md — those are docs, not slides)
- User pastes content with markdown slide patterns: `---` horizontal rules (slide separators), multiple `## Heading` blocks, or bullet-heavy structure

When detected:
1. Read the `.md` file (or capture the pasted content)
2. Confirm with the user: "Looks like a slide deck in Markdown — want me to convert this to an HTML presentation?"
3. If yes -> go to Phase 4B (Markdown Conversion)

### Mode C: Modification Rules

When enhancing existing presentations:

1. **Before adding content:** Count existing elements, check against density limits
2. **Adding images:** Must have `max-height: min(50vh, 400px)`. If slide already has max content, split into two slides
3. **After ANY modification, verify:** `.slide` has `overflow: hidden`, new elements use `clamp()`, images have viewport-relative max-height, content fits at 1280x720
4. **Proactively reorganize:** If modifications will cause overflow, automatically split content and inform the user

### Mode F: Impeccable Context Detection

**This mode activates ALONGSIDE any other mode. It is a modifier, not exclusive.**

On every invocation, before proceeding to any other phase:

1. Check for `.impeccable.md` in the project root / current working directory
2. If found: Read it. Set internal flag `IMPECCABLE_CONTEXT = true`. This unlocks:
   - "Design from my context" option in Phase 2 (Step 2.5)
   - Preset elevation in Phase 2 (Step 2.6)
   - Design elevation enhancements in Phase 3
   - AI Slop Test and design alignment checks in Phase 3.5
3. If NOT found: Proceed normally. In Phase 1, offer a lightweight option to create one.

Mode F does NOT change the flow — it ENHANCES it. A user in Mode A (new presentation) with Mode F active gets all of Mode A's workflow PLUS impeccable enhancements at each phase.

---

## Phase 1: Content Discovery (New Presentations)

**Ask ALL questions in a single message** so the user fills everything out at once.

**When running in Claude Code CLI**, use `AskUserQuestion` tool for each question with selectable options. This gives the user clickable choices instead of requiring typed answers. Ask questions sequentially — each answer may inform the next.

**Question 1 — Language:**
What language is the presentation in? Options: English / 中文 / Bilingual (双语)

**Question 2 — Purpose:**
What is this presentation for? Options: Pitch deck / Teaching-Tutorial / Conference talk / Internal presentation / Academic defense / Product launch

**Question 3 — Length:**
Approximately how many slides? Options: Short 5-10 / Medium 10-20 / Long 20+

**Question 4 — Content:**
Do you have content ready? Options: All content ready / Rough notes / Topic only

**Question 5 — Inline Editing:**
Do you need to edit text directly in the browser after generation? Options: Yes (Recommended) / No

If user has content, ask them to share it.

**Question 6 — Design Context:**

- If `IMPECCABLE_CONTEXT = true`: "I found your design context in `.impeccable.md`. Should I use it to guide the visual style?" Options: Yes, use my design context / No, I'll pick from presets
- If `IMPECCABLE_CONTEXT = false`: "Would you like to establish a design identity for this presentation? This takes ~2 minutes and improves quality." Options: Yes, let's set it up / No, I'll pick from presets

If user says yes and no `.impeccable.md` exists, go to Phase 1.5.

### Step 1.2: Image Evaluation (if images provided)

If user provides images:

1. **Scan** — List all image files
2. **View each image** — Use the Read tool (multimodal)
3. **Evaluate** — For each: what it shows, USABLE or NOT USABLE, dominant colors
4. **Co-design the outline** — Curated images inform slide structure alongside text
5. **Confirm:** "Does this slide outline and image selection look right?"

---

## Phase 1.5: Lightweight Design Context (Optional)

This phase is a LIGHTWEIGHT alternative to {{command_prefix}}teach-impeccable, tailored specifically for presentations. Only triggered when:
- No `.impeccable.md` exists AND user opts in (from Question 6), OR
- User explicitly asks for a custom design-driven style

**If the user wants the FULL design context experience** (codebase exploration, detailed UX questioning, comprehensive design principles), tell them to run `{{command_prefix}}teach-impeccable` separately. Phase 1.5 is the quick path for presentations.

### Three Questions Only:

**Q1 — Audience & Context:**
Who will see this presentation, and in what setting?
(e.g., "investors at a pitch meeting", "engineers at an internal review", "students in a lecture hall")

**Q2 — Brand Personality:**
Describe the feeling in 3 words.
(e.g., "bold, confident, modern" or "warm, approachable, playful" or "elegant, refined, minimal")

**Q3 — Aesthetic Direction:**
Any visual references, anti-references, or strong preferences?
(e.g., "Apple keynote vibes but warmer", "NOT corporate blue", "like a Monocle magazine spread")

### Synthesize and Save:

Write a `.impeccable.md` in the project root / cwd:

```markdown
## Design Context

### Users
[Synthesized from Q1 — who they are, their context, the job to be done]

### Brand Personality
[Synthesized from Q2 — voice, tone, 3-word personality, emotional goals]

### Aesthetic Direction
[Synthesized from Q3 — visual tone, references, anti-references, theme preference]

### Design Principles
[3 principles derived from the answers that should guide all design decisions]
```

Set `IMPECCABLE_CONTEXT = true` and proceed to Phase 2.

---

## Phase 2: Style Discovery

**This is the "show, don't tell" phase.**

### Step 2.0: Style Path

Ask how they want to choose:

- **"Asyre Dark Gold"** (recommended) — The signature Asyre style: dark cinematic backgrounds, amber/gold accents, editorial serif typography, horizontal slide transitions. Pairs perfectly with AI-generated concept art backgrounds. See [ASYRE_BRAND_PRESET.md](ASYRE_BRAND_PRESET.md) for full spec.
- **"Show me options"** — Generate 3 previews based on mood from the 53+ preset library
- **"Browse the gallery"** — Open the local style gallery for visual browsing: `open style-gallery.html` (lightweight preview of all 50+ styles). For the full interactive gallery with live demos, visit: https://next-slide.vercel.app/gallery
- **"I know what I want"** — Pick from preset list directly
- **"Match this reference"** — User provides screenshot/URL, AI matches closest style
- **"Design from my context"** (only shown when `IMPECCABLE_CONTEXT = true`) — Create a CUSTOM style derived from your `.impeccable.md` design context. Uses the same HTML architecture and viewport-base.css, but colors, typography, spacing rhythm, and animation choreography are synthesized from your brand personality and aesthetic direction. Go to Step 2.5.

**If reference match:** Analyze the reference image for colors, typography feel, layout structure. Find the 2-3 closest presets from [STYLE_PRESETS.md](STYLE_PRESETS.md), generate previews of each with the user's content, let them pick.

### Step 2.1: Mood Selection (Guided Discovery)

**When running in Claude Code CLI**, use `AskUserQuestion` tool with selectable options for mood selection and style picking (Steps 2.1 and 2.4).

Ask (multiSelect, max 2):
What feeling should the audience have? Options:

- Impressed/Confident — Professional, trustworthy
- Excited/Energized — Innovative, bold
- Calm/Focused — Clear, thoughtful
- Inspired/Moved — Emotional, memorable
- Fun/Creative — Playful, unique

### Step 2.2: Category Filter

Based on mood, suggest a category:

| Mood                | Suggested Categories               |
| ------------------- | ---------------------------------- |
| Impressed/Confident | Dark Themes, Bold & Creative       |
| Excited/Energized   | Bold & Creative, Specialty         |
| Calm/Focused        | Light Themes                       |
| Inspired/Moved      | Dark Themes, Cultural & Special    |
| Fun/Creative        | Bold & Creative, Cultural & Special|

### Step 2.3: Generate 3 Style Previews

Generate 3 distinct single-slide HTML previews. Read [STYLE_PRESETS.md](STYLE_PRESETS.md) for preset specifications.

**Each preview must be:**
- A single self-contained HTML file (inline CSS/JS, no external dependencies except Google Fonts)
- Showing one animated title slide using the **user's actual title and subtitle** — never use placeholder text like "Lorem Ipsum" or "Your Title Here"
- Saved to `.claude-design/slide-previews/style-a.html`, `style-b.html`, `style-c.html`
- ~50-100 lines each

**After generating all three**, open each in the browser:
```
open .claude-design/slide-previews/style-a.html
open .claude-design/slide-previews/style-b.html
open .claude-design/slide-previews/style-c.html
```

### Step 2.4: User Picks

**When running in Claude Code CLI**, use `AskUserQuestion` tool with options: Style A / Style B / Style C / Mix elements.

Which style preview do you prefer? Options: Style A / Style B / Style C / Mix elements

If "Mix elements", ask for specifics.

### Step 2.5: Custom Style from Design Context

**Only triggered when user picks "Design from my context" in Step 2.0.**

This is where presentations go BEYOND presets. Instead of choosing from 53 predefined styles, the AI creates a custom visual system derived from the project's design context.

**Step 2.5.1: Invoke Design Principles**

Read the following (in this order):
1. `.impeccable.md` — the project's design context (audience, personality, aesthetic direction, principles)
2. Invoke {{command_prefix}}frontend-design principles mentally — apply its typography, color-and-contrast, motion-design, and spatial-design references
3. [STYLE_PRESETS.md](STYLE_PRESETS.md) — use as REFERENCE for what a complete style definition looks like (CSS variable structure, signature elements, font pairing patterns). Do NOT pick a preset — use the structure only.

**Step 2.5.2: Synthesize Custom Style**

From the design context, derive a complete visual system:

| Design Context Field | Maps To |
|---------------------|---------|
| Brand personality | Overall mood, animation tempo, spacing density |
| Aesthetic direction | Color palette, typography pairing, background treatment |
| Design principles | Layout decisions, content hierarchy, decorative element choices |
| Anti-references | What to explicitly AVOID |

Generate a complete `:root` CSS variable block following the exact structure from html-template.md, but with values derived from design context instead of a preset. Include:
- **Color palette** — using OKLCH if the context calls for sophistication; tint neutrals toward brand hue (per frontend-design color reference)
- **Font pairing** — distinctive choices that match brand personality (consult {{command_prefix}}frontend-design typography reference for alternatives to overused fonts)
- **Spacing rhythm** — density that matches audience context (executive = generous, technical = denser)
- **Animation timing and easing** — exponential easing (ease-out-quart/quint/expo), tempo matching audience mood
- **Signature elements** — unique visual details that reflect brand personality (NOT generic glassmorphism, NOT gradient text, NOT neon accents)

**Step 2.5.3: Generate 2 Variations**

Generate 2 single-slide HTML previews showing the custom style:
- **Variation A**: Closer interpretation of design context (faithful to stated direction)
- **Variation B**: More experimental interpretation (creative push beyond stated direction)

Both use the user's actual title. Save to `.claude-design/slide-previews/custom-a.html`, `custom-b.html`.

Open both in the browser:
```
open .claude-design/slide-previews/custom-a.html
open .claude-design/slide-previews/custom-b.html
```

**Step 2.5.4: User Picks or Refines**

**When running in Claude Code CLI**, use `AskUserQuestion` tool with options:

Options: Custom A (faithful) / Custom B (experimental) / Mix elements / Show me presets instead

The "Show me presets instead" escape hatch ensures the user ALWAYS has the safety net of the 53 curated presets. If chosen, go back to Step 2.1.

### Step 2.6: Preset Elevation (when IMPECCABLE_CONTEXT = true and user chose a preset)

When the user picks a preset from the standard flow (Steps 2.1-2.4) BUT `.impeccable.md` design context exists, apply targeted ELEVATION to the preset. The preset is the foundation; design context provides refinements.

**1. Typography elevation**: If the preset uses a common/overused font (Inter, Roboto, Open Sans, Lato, Montserrat), consult `.impeccable.md` aesthetic direction and the {{command_prefix}}frontend-design typography reference to find a MORE distinctive alternative that matches both the preset's mood and the brand personality. Keep the same weight/style relationships.

**2. Color tinting**: Apply the `.impeccable.md` brand direction as subtle adjustments to the preset's palette:
- Tint neutral colors toward the brand hue (even 0.01 chroma in OKLCH creates subconscious cohesion)
- Adjust accent colors if they clash with stated brand direction
- The preset's core palette structure stays — only details shift

**3. Animation refinement**: Match animation tempo to both the preset's mood AND the presentation's audience context from `.impeccable.md`. Executive audiences get slower, more deliberate animations; technical audiences get crisper, faster transitions.

**4. Confirm elevations**: Show the user what you plan to change and WHY. They can:
- Accept all elevations
- Reject individual changes
- Revert to pure preset (escape hatch)

This step is ADDITIVE — the preset structure is preserved, impeccable principles refine the details.

---

## Phase 2.8: AI Background Images (Optional)

After style is confirmed (Phase 2), offer AI-generated background images per slide. This adds atmospheric depth that pure CSS cannot achieve — like the difference between a stage with lighting and a stage without.

### Step 2.8.0: Ask the User

**When running in Claude Code CLI**, use `AskUserQuestion`:

```
header: "Background Images"
question: "Want AI-generated background images for your slides?"
options:
  - label: "Every slide (recommended)"
    description: "Each slide gets a unique atmospheric background image"
  - label: "Key slides only"
    description: "Cover, section dividers, and closing slide"
  - label: "I'll provide my own images"
    description: "I have images ready to use as backgrounds"
  - label: "No images, pure CSS"
    description: "CSS-only backgrounds (fastest, zero image generation)"
```

If user picks "No images, pure CSS" -> skip to Phase 3.
If user picks "I'll provide my own images" -> ask for image paths, proceed to Step 2.8.3.

### Step 2.8.1: Generate Image Prompts

For each slide that needs a background image, generate a short image prompt. The prompt should describe an **atmospheric, abstract background** — NOT a literal illustration of the slide content.

**When using Asyre Dark Gold style** (recommended), follow the proven style system from [ASYRE_BRAND_PRESET.md](ASYRE_BRAND_PRESET.md):

**Prompt template:**
```
Abstract dark background illustration: [slide topic as visual metaphor],
[golden/amber color direction].
Pure black background, very subtle and ethereal, low opacity feel.
Concept art, minimalist, suitable as a faded background image.
No text.
```

**Generation config:**
- Model: `gemini-3-pro-image-preview` (atmosphere quality, NOT flash)
- Aspect ratio: 16:9
- Quality: 2K

**Style rules (CRITICAL):**
- ALWAYS `pure black background`
- ALWAYS `amber and gold` color tone
- ALWAYS `concept art` / `ethereal` aesthetic
- Subject should be `semi-transparent` / `glowing edges` — designed to look good under overlay
- ALWAYS end with `No text, no watermarks`

**Anti-patterns (from Asyre IMAGE_PROMPTS):**
- NO `photorealistic` — use concept art
- NO `neon` / `cyan on dark` / `purple-to-blue gradient` — these are AI slop
- NO text rendered in image — all text goes in HTML
- NO dragons in every image (max 1-2 per deck if thematically appropriate)

**Real examples (from "Taming the Blade" presentation):**
- Power/danger → `a menacing chainsaw dissolving into golden energy particles, blade edge glowing amber`
- Perception → `a single human eye with golden iris, dissolving into amber light particles`
- Lost control → `golden chains shattering and dissolving into amber sparks`
- Self-reflection → `a cracked mirror floating in black void, reflecting amber and golden light`
- Trust → `a pair of hands slowly releasing a golden glowing leash`
- Long-term vision → `a single eternal golden flame burning steady in absolute darkness`

**For non-Asyre styles:** Adapt the prompt template to match the chosen style's color palette. Replace "amber and gold" with the style's accent colors. Keep the structure: `abstract metaphor + color direction + black/dark background + concept art + no text`.

**Key principles:**
- Each slide gets a DIFFERENT visual metaphor — never repeat the same concept
- Abstract > literal (don't illustrate the content, create atmosphere)
- The metaphor should resonate with the slide's emotional intent, not its literal topic
- Match the color direction from the chosen style preset
- If IMPECCABLE_CONTEXT is active, align image mood with `.impeccable.md` aesthetic direction

**Present the prompt list to the user for confirmation before generating.**

### Step 2.8.2: Generate Images

Use the `{{command_prefix}}image-gen` skill to generate background images:

1. Generate images sequentially (one at a time for quality control)
2. Parameters:
   - Aspect ratio: **16:9** (matches slide viewport)
   - Style: match the presentation's mood (dark atmospheric for dark themes, soft/light for light themes)
3. Save images to a `bg/` directory alongside the HTML file:
   ```
   presentation-name/
   ├── index.html
   └── bg/
       ├── 01-cover.jpg
       ├── 02-section-name.jpg
       ├── 03-section-name.jpg
       └── ...
   ```
4. Report progress: "Generated X/N backgrounds" (in user's language)
5. On failure: retry once, then fall back to CSS-only for that slide

**Alternative: Base64 inline** — If the user wants a single self-contained HTML file (no separate `bg/` directory), embed images as base64 data URIs. Warn that file size will be larger (~200KB-1MB per image).

### Step 2.8.3: Image Integration CSS

All background images use the same `.slide-bg` pattern (proven in the 亚马逊 AI 指南):

```css
/* Background image layer — sits behind all content */
.slide-bg {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background-size: cover;
    background-position: center;
    pointer-events: none;
    z-index: 0;
}

/* Content sits above background */
.slide-content {
    position: relative;
    z-index: 1;
}
```

**Opacity/overlay rules (from 踩坑记录):**

| Slide Type | Opacity | Overlay | Rationale |
|-----------|---------|---------|-----------|
| Cover/Title | `opacity: 0.25-0.35` | Dark overlay 70-75% | Image visible but doesn't compete with title text |
| Content (bullets, text) | `opacity: 0.08-0.12` | Optional 55-65% | Subtle atmosphere, text readability is priority |
| Section divider | `opacity: 0.20-0.30` | Dark overlay 65-70% | Stronger presence, fewer text elements |
| Stats/Numbers | `opacity: 0.08-0.10` | Dark overlay 60% | Numbers must be crystal clear |
| Quote slide | `opacity: 0.15-0.20` | Dark overlay 65% | Mood setting without distraction |
| Closing slide | `opacity: 0.25-0.35` | Dark overlay 70-75% | Emotional impact for the ending |
| Code slide | `opacity: 0.05` | Dark overlay 80% | Code readability is paramount |

**For light themes:** Instead of dark overlay, use a light overlay (`background: rgba(255,255,255,0.85)`) and keep image opacity low (`0.05-0.10`). The image becomes a barely perceptible texture.

**CRITICAL:** If text becomes hard to read over the background image, add `text-shadow` as compensation:
```css
.slide-content h1, .slide-content h2 {
    text-shadow: 0 2px 8px rgba(0,0,0,0.5);
}
```

### Step 2.8.4: User-Provided Images

When user provides their own images:
1. **View each image** with the Read tool (multimodal)
2. **Evaluate**: suitable as slide background? Good resolution? Right mood?
3. **Map images to slides**: suggest which image goes with which slide
4. **Confirm mapping** with user before proceeding
5. Follow the same opacity/overlay rules from Step 2.8.3

---

## Phase 3: Generate Presentation

Generate the full presentation using content from Phase 1 and style from Phase 2.

**Before generating, read these supporting files:**

- [html-template.md](html-template.md) — HTML architecture and JS features
- [viewport-base.css](viewport-base.css) — Mandatory CSS (include in full)
- [animation-patterns.md](animation-patterns.md) — Animation reference for the chosen feeling

**Key requirements:**

- Single self-contained HTML file, all CSS/JS inline
- Include the FULL contents of viewport-base.css in the `<style>` block
- Use fonts from Google Fonts or Fontshare — never system fonts
- For Chinese content, always include CJK font in the stack
- Add detailed comments explaining each section
- Navigation: Arrow keys, Space, click buttons, swipe on mobile
- Progress bar at top
- Page counter at bottom
- Always include comprehensive fallback font stacks. For offline/unreliable network scenarios, consider using `font-display: swap` on all Google Font links. If user requests offline mode, embed critical font subsets as base64.

### Background Image Integration (when Phase 2.8 was not skipped)

If the user opted for AI background images or provided their own, integrate them during HTML generation:

1. **Add `.slide-bg` CSS** from Phase 2.8.3 to the `<style>` block
2. **For each slide with a background image**, add the background div as the first child:
   ```html
   <div class="slide" id="slide-N">
       <div class="slide-bg" style="background-image:url(bg/NN-slug.jpg); opacity: 0.10;"></div>
       <div class="slide-content">
           <!-- slide content here -->
       </div>
   </div>
   ```
3. **Set opacity per slide type** according to the table in Phase 2.8.3
4. **Add dark overlay** if needed (for slides with more text):
   ```html
   <div class="slide-bg" style="background-image:url(bg/NN-slug.jpg); opacity: 0.15;"></div>
   <div class="slide-bg-overlay" style="background:rgba(0,0,0,0.65);position:absolute;inset:0;z-index:0;"></div>
   ```
5. **Add `text-shadow`** to headings if text contrast is borderline
6. **If base64 mode**: replace `url(bg/...)` with `url(data:image/jpeg;base64,...)`

**Output structure when using background images:**
```
presentation-name/
├── index.html          ← main presentation
├── bg/                 ← AI-generated or user-provided backgrounds
│   ├── 01-cover.jpg
│   ├── 02-topic.jpg
│   └── ...
└── img/                ← any other images (optional)
```

### Bilingual Support

When language is Chinese or Bilingual:
- Include Chinese web fonts: `Noto Sans SC` for body, `Noto Serif SC` or `LXGW WenKai` for display
- Font stack example: `'LXGW WenKai', 'Noto Serif SC', serif`
- Ensure `lang="zh"` or `lang="zh-en"` on `<html>`
- Text line-height for Chinese: at least 1.8

### Impeccable Generation Enhancements (when IMPECCABLE_CONTEXT = true)

When generating with design context active, apply these additional principles from the impeccable ecosystem:

**For ALL generations (whether using preset or custom style):**
1. Consult {{command_prefix}}frontend-design aesthetics guidelines during generation — specifically the DO/DON'T lists for typography, color, layout, motion, and visual details
2. Apply the AI Slop Test mentally as you generate: avoid the fingerprints of AI work (cyan-on-dark, purple-to-blue gradients, glassmorphism, gradient text on metrics, identical card grids, neon accents on dark backgrounds)
3. If using a preset, apply the elevations confirmed in Step 2.6
4. Reference `.impeccable.md` design principles for content hierarchy decisions — how to split content, which layout types to choose, where to place emphasis

**For custom style generations (from Step 2.5):**
1. The `:root` CSS variables come from Step 2.5.2 synthesis — do NOT fall back to a preset
2. Animation patterns: use [animation-patterns.md](animation-patterns.md) as REFERENCE but adapt timing/easing/choreography to match the design context mood
3. Background treatments: create custom backgrounds informed by design context aesthetic direction (not limited to preset patterns)
4. Decorative elements: design unique signature elements that reflect brand personality — these should be the "one thing someone remembers" about this presentation
5. Apply the {{command_prefix}}frontend-design principle: "Interpret creatively and make unexpected choices that feel genuinely designed for the context. No design should be the same."

**What stays IDENTICAL regardless of impeccable context:**
- viewport-base.css inclusion (non-negotiable)
- html-template.md architecture (non-negotiable)
- Content density limits (non-negotiable)
- Navigation, progress bar, page counter
- Font loading via Google Fonts / Fontshare
- Single self-contained HTML file output
- All accessibility requirements (prefers-reduced-motion, keyboard nav, etc.)

---

## Phase 3.5: Quality Assurance

After generating the HTML in Phase 3, perform a self-validation pass before proceeding to delivery. This catches viewport, font, and density issues before the user sees the result.

**Steps:**

1. **Re-read the generated file** — Use the Read tool to load the full HTML output
2. **Check overflow** — Every `.slide` element must have `overflow: hidden`. If any slide is missing it, add it.
3. **Check font links** — All `<link>` tags for fonts must point to valid Google Fonts (`fonts.googleapis.com`) or Fontshare (`api.fontshare.com`) URLs. Remove or fix any broken/invalid font links.
4. **Check clamp() usage** — All `font-size` and spacing values (`margin`, `padding`, `gap`) must use `clamp()`. Flag and fix any fixed `px` or `rem` values that should be responsive.
5. **Check content density** — Compare each slide's content against the density limits table (Phase 0). If any slide exceeds limits, split it and renumber.
6. **Check CJK fonts** — If any Chinese text exists in the presentation, verify that a CJK font (e.g. `Noto Sans SC`, `Noto Serif SC`, `LXGW WenKai`) is included in both the `<link>` imports and the font stack. Add if missing.
7. **Fix before proceeding** — If any check fails, fix the issue in-place and re-verify. Only proceed to Phase 5 (Delivery) when all checks pass.
8. **AI Slop Test** (when `IMPECCABLE_CONTEXT = true`) — Review the generated presentation against the AI Slop fingerprints from {{command_prefix}}frontend-design:
   - Does it use the "AI color palette" (cyan-on-dark, purple-to-blue gradients, neon accents on dark backgrounds)?
   - Does it have glassmorphism (overused blur effects, glass cards, glow borders)?
   - Does it use gradient text on metrics or headings?
   - Does it have identical card grids (icon + heading + text, repeated)?
   - Does it use rounded rectangles with thick colored border on one side?
   - Does it feel like "every other AI presentation"?
   - If ANY of these: redesign the offending elements to be more distinctive.
9. **Design Context Alignment** (when `IMPECCABLE_CONTEXT = true`) — Compare the output against `.impeccable.md`:
   - Does the typography match the stated aesthetic direction?
   - Do the colors align with brand personality?
   - Does the animation tempo match the audience context?
   - Are the design principles reflected in the layout decisions?
   - If misaligned: adjust to match.
10. **Distinctiveness Check** (when `IMPECCABLE_CONTEXT = true` and a preset was chosen) — Open 2-3 reference presentations from the `styles/` directory that use the SAME preset. Compare. Does this presentation feel meaningfully different because of the design context elevation? If it looks identical to the default preset output, the elevation failed — apply more distinctive choices from the design context.

---

## Phase 4A: PPT Conversion

When converting PowerPoint files:

1. **Extract content** — Run `python scripts/extract-pptx.py <input.pptx> <output_dir>` (install python-pptx if needed: `pip install python-pptx`)
2. **Confirm with user** — Present extracted slide titles, content summaries, and image counts
3. **Style selection** — Proceed to Phase 2 for style discovery
4. **Generate HTML** — Convert to chosen style, preserving all text, images, slide order, and speaker notes

---

## Phase 4B: Markdown Conversion

When converting Markdown content to slides (triggered by Mode E detection):

### Step 4B.1: Parse Markdown Structure

Read the markdown file/content and extract slide structure using these rules:

**Slide boundary detection (in priority order):**
1. `---` (horizontal rule) = explicit slide separator — highest priority
2. `## Heading` (h2) = new slide starts at each h2 — used when no `---` separators exist
3. `# Heading` (h1) = title slide
4. If neither `---` nor `##` patterns are found, split by `### Heading` (h3) blocks

**Content mapping within each slide:**
- `# Heading` -> Title slide (heading + first paragraph as subtitle)
- `## Heading` -> Slide title
- Bullet lists (`- ` or `* `) -> Slide bullet content
- Numbered lists (`1. `) -> Ordered content or step-by-step slides
- `> Blockquote` -> Quote slide
- Code blocks (`` ``` ``) -> Code slide
- `![alt](url)` -> Image slide or image within content slide
- Bold text (`**text**`) -> Emphasized/highlighted content
- Tables -> Data/comparison slide

### Step 4B.2: Auto-Detect Slide Types

Infer the best slide type from content patterns:

| Content Pattern | Slide Type |
|----------------|------------|
| Only a heading + short line | Title slide |
| "vs" or two parallel sections | Comparison slide |
| 3-4 standalone numbers/percentages | Stats slide |
| `> blockquote` | Quote slide |
| Bullet list with 4-6 items | Content slide |
| Bullet list with items that have sub-descriptions | Feature grid |
| Sequential/numbered items with dates or steps | Timeline slide |
| Code block | Code slide |
| Image reference | Image slide |
| Everything else | Content slide (default) |

### Step 4B.3: Confirm Structure

Present the parsed slide outline to the user:
- Slide count, titles, and detected types
- Flag any slides that may exceed content density limits (see Phase 0 table)
- Suggest splits for overloaded slides

### Step 4B.4: Style Selection

If the user hasn't specified a style:
- Proceed to Phase 2 (Style Discovery) for full style selection
- **When running in Claude Code CLI**, use `AskUserQuestion` to ask style preference

If the user specified a style (e.g. "use Swiss Modern" or "dark theme"), skip to Phase 3.

### Step 4B.5: Generate HTML

- Preserve ALL text content from the original markdown — do not summarize or omit
- Convert markdown formatting to HTML: `**bold**` -> `<strong>`, `*italic*` -> `<em>`, etc.
- Apply the chosen style's CSS variables, fonts, colors, and animations
- Respect content density limits — auto-split slides that exceed them
- Include speaker notes as HTML comments if the markdown contains `<!-- notes: ... -->` patterns
- Follow all Phase 3 requirements (viewport-base.css, fonts, navigation, etc.)

---

## Phase 5: Delivery

1. **Clean up** — Delete `.claude-design/slide-previews/` if it exists
2. **Open** — Use `open [filename].html` to launch in browser
3. **"Made with Asyre Presentation" watermark** — The last slide should include a small, subtle watermark line at the bottom:
   - Text: "Made with Asyre Presentation"
   - Style: `color: var(--text-muted); font-size: var(--small-size);`
   - Link to: `https://github.com/codesstar/next-slide` (engine credit)
   - This is **opt-out**: included by default. If the user says "no watermark", omit it.
4. **Summarize** — Tell the user:
   - File location, style name (or "custom from design context"), slide count
   - If background images were generated: mention count and location (`bg/` directory)
   - Navigation: Arrow keys, Space, scroll/swipe, click nav dots
   - How to customize: `:root` CSS variables for colors, font link for typography
   - How to adjust background image opacity: change `opacity` value on `.slide-bg` elements
   - If inline editing was enabled: how to use it
   - If IMPECCABLE_CONTEXT was used: mention which design context elevations were applied

---

## Phase 6: Share & Export (Optional)

Ask: "Want to share this? I can deploy to a live URL or export as PDF."

Options: Deploy to URL / Export to PDF / Both / No thanks

### 6A: Deploy to URL (Vercel)

1. Check Vercel CLI: `npx vercel --version`
2. Check login: `npx vercel whoami`
3. Deploy: `npx vercel --prod`
4. Share the URL

### 6B: Export to PDF

1. Use Playwright to screenshot each slide at 1920x1080
2. Combine into PDF
3. Auto-open the result

---

## Style Library

50+ curated styles across 7 categories. See [STYLE_PRESETS.md](STYLE_PRESETS.md) for full specifications. Browse visually: `open style-gallery.html`

| Category | Styles | Best For |
|----------|--------|----------|
| Dark Themes | Keynote Noir, Bold Signal, Neon Cyber, Terminal Green, Midnight Corporate, Cinema Scope, Dark Botanical, Starfield, Dark Premium, Dark Cinema, Futuristic Blue | Conferences, product launches, tech talks |
| Light Themes | Swiss Modern, Paper & Ink, Notebook Tabs, Pastel Geometry, Morning Brief, Campus White, Soft Landing, Watercolor Wash, Korean Soft, Claymorphism 3D, Wabi-Sabi Zen | Academic, business, teaching |
| Editorial | Editorial Serif, Fashion Editorial, Newsprint Broadsheet, Vintage Editorial | Magazine-style, thought leadership |
| Bold & Creative | Electric Studio, Creative Voltage, Split Pastel, Pop Art, Bold Typography, Neon Brutalism, Memphis Pop | Startups, creative pitches |
| Retro & Vintage | Grainy Retro, Art Deco Gatsby, Risograph Overprint, Vintage Poster, Retro Arcade | Nostalgic themes, stylized talks |
| Artistic | Surrealism Gallery, Scrapbook Portfolio, Blue Collage, Pink Handwritten, Art Nouveau Botanical, Soft Dreamy, Terracotta Earth | Art, design, portfolio showcases |
| Cultural & Special | 东方墨韵, 和風, Gradient Dreams, Blueprint, Bauhaus Primary, Swiss Grid, Aurora Mesh, Chinese Ink Wash | Cultural events, themed presentations |

**Beyond presets:** When `.impeccable.md` exists, you can also generate fully custom styles from design context. See Step 2.5.

---

## Supporting Files

| File | Purpose | When to Read |
|------|---------|-------------|
| [STYLE_PRESETS.md](STYLE_PRESETS.md) | 50+ curated visual presets | Phase 2 |
| [viewport-base.css](viewport-base.css) | Mandatory responsive CSS | Phase 3 |
| [html-template.md](html-template.md) | HTML structure, JS features | Phase 3 |
| [animation-patterns.md](animation-patterns.md) | Animation snippets | Phase 3 |
| [SCENARIO_TEMPLATES.md](SCENARIO_TEMPLATES.md) | Scenario structures, narrative arcs, extra slide types | Phase 1 (when user picks a scenario) & Phase 3 |
| [scripts/extract-pptx.py](scripts/extract-pptx.py) | PPT content extraction | Phase 4A |
| [ASYRE_BRAND_PRESET.md](ASYRE_BRAND_PRESET.md) | Asyre Dark Gold brand style + AI image prompt system | Phase 2 (default), 2.8 |
| [DESIGN_ELEVATION.md](DESIGN_ELEVATION.md) | How impeccable principles elevate presets and custom styles | Phase 2.5, 2.6, 3 |
| `.impeccable.md` (project root) | Project design context — auto-detected | Phase 0, 1, 2, 3, 3.5 |
| {{command_prefix}}frontend-design | Design principles, AI Slop Test, reference library | Phase 2.5, 3, 3.5 |
| {{command_prefix}}teach-impeccable | Full design context gathering (Phase 1.5 is lightweight alternative) | Optional |
| {{command_prefix}}image-gen | AI image generation for slide backgrounds | Phase 2.8 |
