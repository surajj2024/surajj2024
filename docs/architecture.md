# 🏗️ Profile Architecture

> How the `surajj2024` GitHub profile repository is structured and automated.

---

## 📁 Repository Structure

```
surajj2024/
│
├── README.md                    ← Main GitHub profile page
│
├── assets/
│   ├── banner.svg               ← Custom hero banner (1500×420)
│   ├── logo.svg                 ← SK monogram logo (220×220)
│   ├── divider.svg              ← Section divider (1500×40)
│   ├── ai.svg                   ← AI/neural-network icon (200×200)
│   ├── backend.svg              ← Backend/server stack icon (200×200)
│   ├── architecture.svg         ← System architecture icon (200×200)
│   └── avatar-frame.svg         ← Decorative avatar frame (300×300)
│
├── .github/
│   └── workflows/
│       ├── snake.yml            ← Contribution snake animation
│       └── metrics.yml          ← GitHub metrics SVG generator
│
├── docs/
│   ├── architecture.md          ← This file
│   └── branding.md              ← Color palette & design system
│
└── LICENSE                      ← MIT License
```

---

## ⚙️ Automation Workflows

### 🐍 Contribution Snake (`snake.yml`)

Generates an animated SVG of your GitHub contribution graph as a snake game.

| Property | Value |
|----------|-------|
| **Trigger** | Daily at midnight UTC + manual dispatch |
| **Action** | `Platane/snk@v3` |
| **Output branch** | `output` |
| **Files generated** | `github-contribution-grid-snake.svg` (light) + `github-contribution-grid-snake-dark.svg` (dark) |

**Usage in README:**
```html
<picture>
  <source media="(prefers-color-scheme: dark)"
    srcset="https://raw.githubusercontent.com/surajj2024/surajj2024/output/github-contribution-grid-snake-dark.svg"/>
  <source media="(prefers-color-scheme: light)"
    srcset="https://raw.githubusercontent.com/surajj2024/surajj2024/output/github-contribution-grid-snake.svg"/>
  <img alt="Contribution Snake" src="..."/>
</picture>
```

---

### 📊 GitHub Metrics (`metrics.yml`)

Generates a detailed metrics SVG using [lowlighter/metrics](https://github.com/lowlighter/metrics).

| Property | Value |
|----------|-------|
| **Trigger** | Every 12 hours + manual dispatch |
| **Action** | `lowlighter/metrics@latest` |
| **Output** | `assets/metrics.svg` committed to `main` |
| **Required secret** | `METRICS_TOKEN` (GitHub PAT with `read:user` scope) |

**Plugins enabled:**
- 🌐 Languages breakdown
- 📅 Isometric contribution calendar (6 months)
- 💡 Coding habits & charts
- 📏 Lines of code changed
- 🔄 Issue/PR follow-up
- ⭐ Starred repositories
- 🏷️ Topics
- 🏆 Achievements

---

## 🎨 Design System

See [`branding.md`](./branding.md) for the full color palette, typography, and design tokens.

---

## 🔐 Required Secrets

| Secret | Purpose | Scope |
|--------|---------|-------|
| `GITHUB_TOKEN` | Auto-provided by GitHub Actions | Built-in |
| `METRICS_TOKEN` | Personal Access Token for metrics | `read:user`, `repo` |

To add `METRICS_TOKEN`:
1. Go to GitHub → Settings → Developer Settings → Personal Access Tokens
2. Create a token with `read:user` and `repo` scopes
3. Add it to your repo: Settings → Secrets → Actions → New repository secret

---

## 🚀 Setup Instructions

1. **Fork or clone** this repository as your `<username>/<username>` special repo
2. **Enable GitHub Actions** in the Actions tab
3. **Add `METRICS_TOKEN`** secret (see above)
4. **Trigger workflows manually** once to generate initial outputs
5. **Update README.md** with your actual LinkedIn/email links

---

*Last updated: 2026 · Suraj Kumar*
