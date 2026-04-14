# README Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Redesign the GitHub profile README with an ASCII art header, about blurb, project cards, and a cleaned-up tech stack — terminal/hacker aesthetic, no fake shell syntax.

**Architecture:** Single-file rewrite of `README.md`. Four sequential tasks: replace header, replace Now section + add About, add Projects section, clean up Tech Stack. Each task is an isolated edit + commit.

**Tech Stack:** GitHub Flavored Markdown, shields.io badges, box-drawing character ASCII art, HTML `<div>`/`<pre>` for centering.

---

## File Map

| File | Change |
|---|---|
| `README.md` | Full rewrite across 4 tasks |

---

### Task 1: Replace header with ASCII art

**Files:**
- Modify: `README.md` lines 1–8

Current header (lines 1–8):
```html
<div align="center">
  <h1>Rayan Rane</h1>
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&duration=3000&pause=1000&color=7AA2F7&center=true&vCenter=true&width=435&lines=cs+student+%40+northeastern;building+is+fun" alt="Typing SVG" />
  <br><br>
  <a href="https://linkedin.com/in/rayanrane"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white"/></a>
  &nbsp;
  <a href="mailto:rane.r@northeastern.edu"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white"/></a>
</div>
```

- [ ] **Step 1: Replace lines 1–8 with the new ASCII header**

Replace the entire header block (lines 1–8) with:

```html
<div align="center">

<pre>
██████╗  █████╗ ██╗   ██╗ █████╗ ███╗   ██╗
██╔══██╗██╔══██╗╚██╗ ██╔╝██╔══██╗████╗  ██║
██████╔╝███████║ ╚████╔╝ ███████║██╔██╗ ██║
██╔══██╗██╔══██║  ╚██╔╝  ██╔══██║██║╚██╗██║
██║  ██║██║  ██║   ██║   ██║  ██║██║ ╚████║
╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═══╝

██████╗  █████╗ ███╗   ██╗███████╗
██╔══██╗██╔══██╗████╗  ██║██╔════╝
██████╔╝███████║██╔██╗ ██║█████╗  
██╔══██╗██╔══██║██║╚██╗██║██╔══╝  
██║  ██║██║  ██║██║ ╚████║███████╗
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚══════╝
</pre>

`cs @ northeastern`

<a href="https://linkedin.com/in/rayanrane"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white"/></a>
&nbsp;
<a href="mailto:rane.r@northeastern.edu"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white"/></a>

</div>
```

Note: The blank line after `<div align="center">` and before `</div>` is required for GitHub Flavored Markdown to render the HTML block correctly. The `<pre>` tag ensures monospace rendering of the box-drawing characters. `RAYAN` and `RANE` are on separate line-groups, each 6 lines tall, separated by a blank line inside `<pre>`.

- [ ] **Step 2: Verify the edit looks correct**

Run:
```bash
cat -n README.md | head -25
```

Expected: Lines 1–21 show the new `<div>` block with `<pre>` ASCII art, tagline, and badges. The old `<h1>` and `<img src="readme-typing-svg...">` must not appear.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: replace header with ASCII art block"
```

---

### Task 2: Replace Now section with About blurb

**Files:**
- Modify: `README.md` — the `## Now` section (currently lines 12–17 after Task 1)

Current Now section (lines 12–17):
```markdown
## Now

building → [RateMyHusky](https://github.com/RayanR000/RateMyHusky)

professor ratings for NEU students
```

- [ ] **Step 1: Replace the Now section with the About blurb**

Replace from `## Now` through `professor ratings for NEU students` with:

```markdown
i build tools people actually use.  
currently @ northeastern, shipping between semesters.
```

Two trailing spaces after the first line (`use.  `) force a line break in GFM — this keeps both sentences visually separated without a blank paragraph gap between them.

- [ ] **Step 2: Verify**

Run:
```bash
cat -n README.md | head -30
```

Expected: The `## Now` heading and old content are gone. The two bio lines appear between the first `---` divider and the second `---` divider. No `## Now` heading — the bio is headingless.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: replace Now section with outcome-focused about blurb"
```

---

### Task 3: Add Projects section

**Files:**
- Modify: `README.md` — insert Projects section between About blurb and Tech Stack

After Task 2, the file structure is:
```
[header div]
---
[about blurb — 2 lines]
---
## Tech Stack
...
```

The Projects section goes between the second `---` and `## Tech Stack`.

- [ ] **Step 1: Insert the Projects section**

Between the second `---` divider and `## Tech Stack`, insert:

```markdown
── projects ──────────────────────────────

**[RateMyHusky](https://github.com/RayanR000/RateMyHusky)**  
professor discovery & rating platform for NEU students  
`next.js` · `postgresql` · `google oauth` · `tailwind`

**[MOMENTUM](https://github.com/RayanR000/MOMENTUM)**  
ai-powered weightlifting form analyzer  
`python` · `fastapi` · `react` · `computer vision`

---

```

Notes:
- `── projects ──────────────────────────────` is plain markdown text, not a code block — it renders as a decorative label line in the monospace/terminal style.
- Each project name is bold + a markdown link.
- Two trailing spaces after the name line (`RateMyHusky)**  `) force a line break before the description.
- Tech tags use backtick inline code, separated by ` · ` (middle dot, not a dash).
- The trailing `---` closes the Projects section before Tech Stack begins.

- [ ] **Step 2: Verify**

Run:
```bash
cat -n README.md
```

Expected: Projects section appears between the About blurb and `## Tech Stack`. Both RateMyHusky and MOMENTUM cards are present. No orphaned `---` dividers.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add projects section with RateMyHusky and MOMENTUM cards"
```

---

### Task 4: Clean up Tech Stack section

**Files:**
- Modify: `README.md` — Tech Stack section

Changes:
1. Rename `**Languages**` → `**languages**` (lowercase)
2. Rename `**Frontend**` → `**frontend**` (lowercase)
3. Rename `**Backend & Data**` → `**backend**` (lowercase, shorter)
4. Rename `**DevOps**` → `**devops**` (lowercase)
5. Remove the `CSS3` badge line entirely
6. Remove the `Vite` badge line entirely

- [ ] **Step 1: Lowercase all four category headings**

Make these four replacements in `README.md`:

| Find | Replace |
|---|---|
| `**Languages**` | `**languages**` |
| `**Frontend**` | `**frontend**` |
| `**Backend & Data**` | `**backend**` |
| `**DevOps**` | `**devops**` |

- [ ] **Step 2: Remove the CSS3 badge line**

Remove this line entirely (including its trailing newline):
```
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
```

- [ ] **Step 3: Remove the Vite badge line**

Remove this line entirely (including its trailing newline):
```
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
```

- [ ] **Step 4: Verify the final README**

Run:
```bash
cat -n README.md
```

Expected output — full file should match exactly:

```markdown
<div align="center">

<pre>
██████╗  █████╗ ██╗   ██╗ █████╗ ███╗   ██╗
██╔══██╗██╔══██╗╚██╗ ██╔╝██╔══██╗████╗  ██║
██████╔╝███████║ ╚████╔╝ ███████║██╔██╗ ██║
██╔══██╗██╔══██║  ╚██╔╝  ██╔══██║██║╚██╗██║
██║  ██║██║  ██║   ██║   ██║  ██║██║ ╚████║
╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═══╝

██████╗  █████╗ ███╗   ██╗███████╗
██╔══██╗██╔══██╗████╗  ██║██╔════╝
██████╔╝███████║██╔██╗ ██║█████╗  
██╔══██╗██╔══██║██║╚██╗██║██╔══╝  
██║  ██║██║  ██║██║ ╚████║███████╗
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚══════╝
</pre>

`cs @ northeastern`

<a href="https://linkedin.com/in/rayanrane"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white"/></a>
&nbsp;
<a href="mailto:rane.r@northeastern.edu"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white"/></a>

</div>

---

i build tools people actually use.  
currently @ northeastern, shipping between semesters.

---

── projects ──────────────────────────────

**[RateMyHusky](https://github.com/RayanR000/RateMyHusky)**  
professor discovery & rating platform for NEU students  
`next.js` · `postgresql` · `google oauth` · `tailwind`

**[MOMENTUM](https://github.com/RayanR000/MOMENTUM)**  
ai-powered weightlifting form analyzer  
`python` · `fastapi` · `react` · `computer vision`

---

## Tech Stack

**languages**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

**frontend**

![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)

**backend**

![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![CockroachDB](https://img.shields.io/badge/CockroachDB-6933FF?style=flat&logo=cockroachlabs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Google OAuth](https://img.shields.io/badge/Google_OAuth-4285F4?style=flat&logo=google&logoColor=white)

**devops**

![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=flat&logo=railway&logoColor=white)
```

Check: `CSS3` and `Vite` badges must not appear. All four category headings must be lowercase. Both project cards must be present.

- [ ] **Step 5: Commit**

```bash
git add README.md
git commit -m "feat: clean up tech stack — lowercase categories, remove CSS3 and Vite"
```
