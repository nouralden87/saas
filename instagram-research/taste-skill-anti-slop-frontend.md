# Taste-Skill — Anti-Slop Frontend Framework for AI Agents

> **Source:** [Instagram Reel by gittrend.io](https://www.instagram.com/reel/DZg4DOPgDk_/) (June 12, 2026)
> **Repo:** [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill)

---

## 📊 Quick Stats

| Metric | Value |
|---|---|
| Stars | ⭐ 50,891 |
| Forks | 3,505 |
| Open Issues | 33 |
| License | MIT |
| Language | JavaScript |
| Created | Feb 19, 2026 |
| Last Updated | Jun 25, 2026 |
| Contributors | Leonxlnx (125 commits) + 4 others |
| Website | [tasteskill.dev](https://tasteskill.dev) |
| Vercel OSS | ✅ Sponsored |

---

## 🎯 What It Is

Portable **Agent Skills** (SKILL.md files) that upgrade AI-built frontend interfaces — stronger layout, typography, motion, and spacing instead of boilerplate-looking UIs. Also includes image-generation skills for reference boards (web, mobile, brand kits).

The core idea: AI coding agents (Claude Code, Codex, Cursor, ChatGPT) tend to produce bland, generic, "slop" frontends. Taste-Skill injects design taste into the agent's output by providing structured design rules as portable SKILL.md files.

---

## 🔧 All Skills (14 total)

### Implementation Skills (output code)

| Skill | Install Name | Description |
|---|---|---|
| **taste-skill** | `design-taste-frontend` | 🆕 v2 (experimental) — Main skill with 3 dials: VARIANCE/MOTION/DENSITY |
| **taste-skill-v1** | `design-taste-frontend-v1` | Original v1, preserved for compatibility |
| **gpt-tasteskill** | `gpt-taste` | Stricter variant for GPT/Codex with higher layout variance |
| **image-to-code-skill** | `image-to-code` | Image→analyze→code pipeline: generate references then implement |
| **redesign-skill** | `redesign-existing-projects` | Audit existing UI first, then fix layout/spacing/hierarchy |
| **soft-skill** | `high-end-visual-design` | Polished, calm, expensive UI with softer contrast, spring motion |
| **output-skill** | `full-output-enforcement` | Forces model to ship complete output (no placeholder comments) |
| **minimalist-skill** | `minimalist-ui` | Editorial product UI — Notion/Linear vibes |
| **brutalist-skill** | `industrial-brutalist-ui` | Hard mechanical: Swiss type, sharp contrast, experimental layout |
| **stitch-skill** | `stitch-design-taste` | Google Stitch-compatible rules + DESIGN.md export |

### Image Generation Skills (output images only)

| Skill | Install Name | Description |
|---|---|---|
| **imagegen-frontend-web** | `imagegen-frontend-web` | Website comps: hero, landing, multi-section |
| **imagegen-frontend-mobile** | `imagegen-frontend-mobile` | Mobile screens and flows |
| **brandkit** | `brandkit` | Brand-kit boards: logos, palettes, type, identity |

---

## 🎛️ Core Design Dials (taste-skill v2)

Three 1-10 dials control the output:

- **DESIGN_VARIANCE** — Layout experimentation (lower=clean/centered, higher=asymmetric/modern)
- **MOTION_INTENSITY** — Animation depth (lower=hover only, higher=scroll/magnetic)
- **VISUAL_DENSITY** — Information per viewport (lower=spacious, higher=dense dashboards)

---

## 📥 Installation

```bash
# Install all skills
npx skills add https://github.com/Leonxlnx/taste-skill

# Install specific skill
npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"
```

Uses **Vercel's Agent Skills** standard (`npx skills` CLI). Compatible with Claude Code, Cursor, Codex, and ChatGPT.

---

## 🧭 Which Skill To Use

1. **Start with `taste-skill`** — safest general default (v2 experimental)
2. **Use `gpt-taste`** — stricter GPT/Codex-oriented rules
3. **Use `image-to-code-skill`** — image → analyze → code website workflows
4. **Use `redesign-skill`** — improve existing codebase instead of greenfield
5. **Add `soft-skill` / `minimalist-skill` / `brutalist-skill`** — when visual direction is already chosen
6. **Add `output-skill`** — if agent keeps truncating output

---

## 💡 Relevance to Our Projects

- **Hermes Agent frontend**: Can use taste-skill to improve any web UI Hermes generates
- **SaaS tools**: All free-tools-marketing landing pages benefit from anti-slop design rules
- **Design system**: The dial-based approach (VARIANCE/MOTION/DENSITY) is a reusable pattern for agent-controlled design generation
- **Image-to-code pipeline**: Generate reference designs first, then implement — useful for rapid prototyping

---

## 🔗 Links

- **Repo:** https://github.com/Leonxlnx/taste-skill
- **Website:** https://tasteskill.dev
- **Creator:** [@lexnlin](https://x.com/lexnlin) + [@blueemi99](https://x.com/blueemi99)
- **Sponsor:** [Emil Kowalski](https://github.com/emilkowalski) — [animations.dev](https://animations.dev)
- **Vercel OSS Program:** Sponsored
- **Topics:** agent, ai, claude, claude-code, codex, coding, design, frontend, lowcode, nocode, skill, vibecoding

---

## 📝 Instagram Post

- **Account:** [gittrend.io](https://www.instagram.com/gittrend.io)
- **Date:** June 12, 2026 (1 week ago as of research)
- **Likes:** 183
- **Caption:** "If your AI keeps spitting out bland frontends, taste-skill helps the agent design nicer layouts and visuals. More like this → gittrend.io"
- **Hashtags:** #opensource #github #aidedesign #frontend #ux #ai #devtools

---

*Researched: June 25, 2026*
