# 🎨 Branding & Design System

> Visual identity guidelines for the `surajj2024` GitHub profile.

---

## 🎨 Color Palette

### Primary Colors

| Name | Hex | Usage |
|------|-----|-------|
| **GitHub Dark** | `#0D1117` | Primary background |
| **GitHub Dark 2** | `#161B22` | Card / secondary background |
| **GitHub Border** | `#30363D` | Borders, dividers |
| **GitHub Muted** | `#21262D` | Pill / tag backgrounds |

### Accent Colors

| Name | Hex | Usage |
|------|-----|-------|
| **Electric Blue** | `#58A6FF` | Primary accent, links, highlights |
| **Deep Purple** | `#7C3AED` | Secondary accent, gradients |
| **Emerald Green** | `#3FB950` | Success, status indicators |
| **Coral Red** | `#F78166` | Warnings, architecture diagrams |
| **Hot Pink** | `#E10098` | GraphQL branding |
| **Laravel Red** | `#FF2D20` | Laravel branding |
| **AWS Orange** | `#FF9900` | AWS branding |
| **Python Blue** | `#3776AB` | Python branding |

### Text Colors

| Name | Hex | Usage |
|------|-----|-------|
| **Primary Text** | `#F0F6FC` | Headings, important text |
| **Secondary Text** | `#C9D1D9` | Body text |
| **Muted Text** | `#8B949E` | Subtitles, captions |

---

## 🌈 Gradients

### Primary Gradient (Blue → Purple)
```css
background: linear-gradient(135deg, #58A6FF 0%, #7C3AED 100%);
```

### Hero Gradient (Dark)
```css
background: linear-gradient(135deg, #0D1117 0%, #161B22 100%);
```

### Divider Gradient (Fade in/out)
```css
background: linear-gradient(90deg,
  transparent 0%,
  #58A6FF 15%,
  #7C3AED 50%,
  #58A6FF 85%,
  transparent 100%
);
```

### Tri-color Gradient (Blue → Purple → Green)
```css
background: linear-gradient(135deg, #58A6FF 0%, #7C3AED 50%, #3FB950 100%);
```

---

## 🔤 Typography

### Font Stack
```css
font-family: 'JetBrains Mono', 'Fira Code', 'Segoe UI', system-ui, sans-serif;
```

### Scale

| Element | Size | Weight |
|---------|------|--------|
| Hero Name | 72px | 800 |
| Section Title | 28–32px | 700 |
| Subtitle | 17–20px | 400–600 |
| Body | 14–16px | 400 |
| Labels / Pills | 11–13px | 600 |
| Captions | 10–12px | 400 |

---

## 🖼️ Asset Specifications

| Asset | Dimensions | Format | Purpose |
|-------|-----------|--------|---------|
| `banner.svg` | 1500 × 420 | SVG | Hero banner at top of README |
| `logo.svg` | 220 × 220 | SVG | SK monogram, used inline |
| `divider.svg` | 1500 × 40 | SVG | Section separator |
| `ai.svg` | 200 × 200 | SVG | AI section icon |
| `backend.svg` | 200 × 200 | SVG | Backend section icon |
| `architecture.svg` | 200 × 200 | SVG | Architecture section icon |
| `avatar-frame.svg` | 300 × 300 | SVG | Decorative avatar frame |

---

## 🧩 Design Principles

1. **Dark-first** — All assets are designed for GitHub's dark theme (`#0D1117` base)
2. **Consistent gradients** — Always use Blue→Purple as the primary gradient direction
3. **Subtle depth** — Use low-opacity glow effects (`opacity: 0.03–0.08`) for ambient light
4. **Grid patterns** — Use dot/grid patterns at low opacity for texture
5. **Rounded corners** — `rx="6"` for cards, `rx="16"` for pills, `rx="44"` for logo
6. **Accent dots** — Use cardinal-point dots (top/bottom/left/right) on circular elements
7. **Status green** — Always use `#3FB950` for "online" / "available" indicators

---

## 📐 Layout Guidelines

### README Sections
- Each section separated by `divider.svg`
- Stats/analytics always `align="center"`
- Tech stack icons grouped by category
- Project cards use `>` blockquote for description + badge row + code block for features

### Badge Style
- **Profile badges**: `style=for-the-badge` with `color=0D1117&labelColor=161B22`
- **Project badges**: `style=flat-square` with technology brand colors
- **Status badges**: `style=for-the-badge` with full color

---

## 🔗 External Services Used

| Service | Purpose | URL |
|---------|---------|-----|
| GitHub Readme Stats | Stats cards | `github-readme-stats.vercel.app` |
| Streak Stats | Contribution streak | `streak-stats.demolab.com` |
| Activity Graph | Contribution graph | `github-readme-activity-graph.vercel.app` |
| Trophy | GitHub trophies | `github-profile-trophy.vercel.app` |
| Typing SVG | Animated typing | `readme-typing-svg.demolab.com` |
| Skill Icons | Tech stack icons | `skillicons.dev` |
| Shields.io | Custom badges | `shields.io` |
| Profile Views | View counter | `komarev.com/ghpvc` |

---

*Last updated: 2026 · Suraj Kumar*
