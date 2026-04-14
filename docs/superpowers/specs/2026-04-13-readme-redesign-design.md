# GitHub Profile README Redesign — Design Spec

**Date:** 2026-04-13  
**Status:** Approved  

---

## Goal

Redesign the GitHub profile README to be unique, cool, and professional. Replace the generic typing SVG header with ASCII art and add meaningful content while keeping the page tight and scannable.

---

## Aesthetic Direction

**Dark/technical — ASCII art + dark badges variant.**

- ASCII block-letter art header (no fake shell syntax, no terminal sessions)
- Monospace copy, lowercase tone
- Tokyo Night color palette retained for badges (`#7AA2F7` blue)
- Horizontal rule dividers with inline labels for section separation
- No GitHub stats cards (removed per prior session)

---

## Sections

### 1. Header

- ASCII block-letter art spelling `RAYAN RANE` inside a `<pre>` block, centered with `<div align="center">`
- Font style: box-drawing characters (█ / ╗ / ═ style — "ANSI Shadow" or "Block" from figlet/taag)
- Replaces the `readme-typing-svg` — the ASCII art is custom and non-generic
- Tagline below: `cs @ northeastern`
- LinkedIn and email shields.io badges below the tagline (retain existing URLs)

### 2. About

Two lines, lowercase, **no `##` section heading** (flows directly after the header divider), outcome-focused tone:

```
i build tools people actually use.
currently @ northeastern, shipping between semesters.
```

### 3. Projects

Section heading: `── projects ──────────────────────────────` as plain markdown text (not a code block), followed by a blank line.

Two cards, each with:
- Project name as a markdown link
- One-line description (lowercase)
- Key technologies as inline `code` tags

**Card 1 — RateMyHusky**
- Link: `https://github.com/RayanR000/RateMyHusky`
- Description: professor discovery & rating platform for NEU students
- Tech: `next.js` · `postgresql` · `google oauth` · `tailwind`

**Card 2 — MOMENTUM**
- Link: `https://github.com/RayanR000/MOMENTUM`
- Description: ai-powered weightlifting form analyzer
- Tech: `python` · `fastapi` · `react` · `computer vision`

### 4. Tech Stack

Retain shields.io badges (`style=flat`). Remove `CSS3` (redundant with Tailwind) and `Vite` (not a meaningful stack highlight). Four categories:

| Category | Badges |
|---|---|
| languages | TypeScript, Python, JavaScript |
| frontend | React, Next.js, TailwindCSS |
| backend | Flask, FastAPI, PostgreSQL, CockroachDB, Google OAuth |
| devops | Vercel, Railway |

---

## What's Removed

- `readme-typing-svg` animated header — replaced by ASCII art
- GitHub stats/streak/top-langs cards — previously removed, not re-added
- `CSS3` badge
- `Vite` badge

---

## What's Added

- ASCII art header in `<pre>` block
- About blurb (2 lines)
- Projects section with two formatted cards (RateMyHusky, MOMENTUM)

---

## Files Changed

- `README.md` — full rewrite
