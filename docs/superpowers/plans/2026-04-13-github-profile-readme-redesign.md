# GitHub Profile README Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Redesign `README.md` in the RayanR000 profile repo to be visually appealing and professional for both recruiters and developers.

**Architecture:** Three sections — animated header with contact badges, organized tech stack badge grid, centered "Now" line. No stats widgets. One external dependency: `readme-typing-svg.demolab.com`.

**Tech Stack:** GitHub-flavored Markdown, HTML (for centering), shields.io badges, readme-typing-svg

---

### Task 1: Rewrite the header section

**Files:**
- Modify: `README.md` (lines 1–14, the current `<h1>` + `<p>` + contact block)

- [ ] **Step 1: Replace the current header block**

Open `README.md` and replace everything from line 1 through the first `---` (not including the `---`) with:

```html
<div align="center">
  <h1>Rayan Rane</h1>
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&duration=3000&pause=1000&color=6E40C9&center=true&vCenter=true&width=500&lines=Full-stack+developer;CS+%40+Northeastern+University;Building+things+end-to-end" alt="Typing SVG" />
  <br/><br/>
  <a href="https://linkedin.com/in/rayanrane"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white"/></a>
  &nbsp;
  <a href="mailto:rane.r@northeastern.edu"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white"/></a>
</div>
```

- [ ] **Step 2: Verify the header renders correctly**

Push to GitHub (or use a local Markdown previewer) and confirm:
- Name appears as a large centered heading
- Typing animation cycles through the 3 phrases
- LinkedIn and Email badges appear inline and centered below

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "redesign: animated header with centered contact badges"
```

---

### Task 2: Reorganize the Tech Stack section

**Files:**
- Modify: `README.md` (the Tech Stack section)

- [ ] **Step 1: Replace the Tech Stack section**

Find the `## Tech Stack` section and replace it entirely with:

```markdown
## Tech Stack

**Languages**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

**Frontend**

![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)

**Backend & Data**

![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![CockroachDB](https://img.shields.io/badge/CockroachDB-6933FF?style=flat&logo=cockroachlabs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Google OAuth](https://img.shields.io/badge/Google_OAuth-4285F4?style=flat&logo=google&logoColor=white)

**DevOps**

![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=flat&logo=railway&logoColor=white)
```

Key change: Google OAuth badge moves from its own "Auth" heading into the "Backend & Data" row. The standalone "Auth" heading is removed.

- [ ] **Step 2: Verify badge layout**

Confirm all four category rows render correctly and Google OAuth appears inline with the other backend badges.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "redesign: consolidate tech stack into 4 clean rows"
```

---

### Task 3: Style the Now section

**Files:**
- Modify: `README.md` (the Now section)

- [ ] **Step 1: Replace the Now section**

Find the `## Now` section and replace it with:

```markdown
## Now

<div align="center">

Building **[RateMyHusky](https://github.com/RayanR000/RateMyHusky)** — professor discovery & rating platform for NEU students

</div>
```

The blank lines inside the `<div>` are required for GitHub to render the Markdown bold/link syntax inside the HTML block.

- [ ] **Step 2: Verify centering**

Confirm the "Now" line renders centered with the bold project name and working link.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "redesign: center Now section for visual weight"
```

---

### Task 4: Final review

- [ ] **Step 1: View the live profile**

Visit `https://github.com/RayanR000` and confirm:
- Header animation plays
- Four clean tech stack rows with no orphaned "Auth" heading
- "Now" line is centered and the link works
- No broken badge images

- [ ] **Step 2: Push if not already pushed**

```bash
git push origin main
```
