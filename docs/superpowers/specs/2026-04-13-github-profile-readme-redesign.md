# GitHub Profile README Redesign

**Date:** 2026-04-13  
**Status:** Approved  
**Audience:** Recruiters and developers equally

---

## Goal

Redesign the GitHub profile README (RayanR000/RayanR000) to be visually appealing and professional for both recruiters scanning quickly and developers assessing technical depth.

## Chosen Approach

**Option B — Structured with Visual Hierarchy**

Animated typing subheader, organized badge grid, and a "Now" section. No heavy stats widgets. One external dependency: `readme-typing-svg.demolab.com`.

---

## Section Design

### 1. Header

- Centered `<h1>` with name: **Rayan Rane**
- Animated typing SVG (via `readme-typing-svg.demolab.com`) cycling through:
  - `Full-stack developer`
  - `CS @ Northeastern University`
  - `Building things end-to-end`
- LinkedIn and Email badges, centered, inline, below the animation
- Horizontal rule separator

### 2. Tech Stack

Four rows of inline shield badges, one row per category:

| Category | Badges |
|---|---|
| Languages | TypeScript, Python, JavaScript |
| Frontend | React, Vite, CSS3 |
| Backend & Data | Flask, CockroachDB, PostgreSQL, Google OAuth |
| DevOps | Vercel, Railway |

Google OAuth is moved from its own "Auth" heading into Backend & Data — it is a backend concern and the separate heading added visual clutter.

Horizontal rule separator after.

### 3. Now

Single line linking to active project, wrapped in a centered `<p>` for visual weight:

> Building **RateMyHusky** — professor discovery & rating platform for NEU students

---

## Non-Goals

- No GitHub stats widgets (unreliable, noisy)
- No contribution snake animation
- No "About Me" prose section (removed by user preference)
- No separate "Let's Connect" section (contact lives in header)

---

## Implementation Notes

- All HTML uses `align="center"` for GitHub markdown compatibility
- Typing SVG color: `#6E40C9` (purple, neutral and professional)
- Badge style: `flat` throughout for consistency
- File: `README.md` at repo root
