<div align="center">

# 🌐 Portfolio

### Modern developer portfolio — dark theme, fast, and fully customizable

<br/>

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)
[![Deploy on Vercel](https://img.shields.io/badge/Deploy_on-Vercel-000000?style=flat-square&logo=vercel)](https://vercel.com)

</div>

---

## 🌟 Overview

A sleek, modern developer portfolio built with React, TypeScript, and Tailwind CSS. Features a dark GitHub-inspired theme, smooth animations, and sections for showcasing your projects, skills, articles, and contact info.

**Live Demo:** [surajkumar.dev](https://surajkumar.dev) *(replace with your URL)*

---

## ✨ Features

- 🌙 **Dark Theme** — GitHub-inspired dark color palette
- ⚡ **Blazing Fast** — Built with Vite for instant HMR and optimized builds
- 📱 **Fully Responsive** — Mobile-first design, looks great on all devices
- 🎨 **Smooth Animations** — Framer Motion powered transitions and scroll effects
- 🔍 **SEO Optimized** — Meta tags, Open Graph, structured data
- 📊 **GitHub Integration** — Live GitHub stats via API
- 📝 **Blog/Articles** — Medium RSS feed integration
- 🎯 **Easy Customization** — Single config file to update all content
- 🚀 **One-click Deploy** — Vercel / Netlify / GitHub Pages ready

---

## 🖼️ Sections

| Section | Description |
|---------|-------------|
| 🏠 **Hero** | Animated intro with name, role, and CTA buttons |
| 👤 **About** | Bio, skills, and quick facts |
| 🛠️ **Tech Stack** | Visual tech stack with icons |
| 🌟 **Projects** | Featured project cards with links |
| 📝 **Articles** | Latest Medium articles (auto-fetched) |
| 📊 **GitHub Stats** | Live contribution stats |
| 🤝 **Contact** | Contact form + social links |

---

## 🚀 Quick Start

### Installation

```bash
git clone https://github.com/surajj2024/portfolio.git
cd portfolio

npm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Customize

Edit `src/config/portfolio.ts` to update all your information:

```typescript
// src/config/portfolio.ts
export const config = {
  name: "Suraj Kumar",
  role: "AI Backend Engineer",
  tagline: "Building Intelligent Enterprise Systems",
  location: "India 🇮🇳",
  email: "surajjkumar9608@gmail.com",

  social: {
    github: "https://github.com/surajj2024",
    linkedin: "https://www.linkedin.com/in/suraj-kumar-5b34a61b3/",
    medium: "https://medium.com/@surajjkumar9608",
    twitter: "",
  },

  skills: [
    { name: "Laravel", icon: "laravel", color: "#FF2D20" },
    { name: "Python", icon: "python", color: "#3776AB" },
    { name: "AWS", icon: "aws", color: "#FF9900" },
    { name: "GraphQL", icon: "graphql", color: "#E10098" },
    // ... add more
  ],

  projects: [
    {
      title: "Enterprise SaaS Platform",
      description: "Multi-tenant strategic planning platform with AI workflows",
      tags: ["Laravel", "GraphQL", "PostgreSQL", "AWS"],
      github: "https://github.com/surajj2024/enterprise-ai",
      demo: "",
      featured: true,
    },
    // ... add more projects
  ],

  medium: {
    username: "surajjkumar9608",
    maxArticles: 3,
  },

  github: {
    username: "surajj2024",
    showStats: true,
    showStreak: true,
    showTopLangs: true,
  },
};
```

---

## 📁 Project Structure

```
portfolio/
├── src/
│   ├── components/
│   │   ├── Hero/            ← Hero section
│   │   ├── About/           ← About section
│   │   ├── TechStack/       ← Skills & tech icons
│   │   ├── Projects/        ← Project cards
│   │   ├── Articles/        ← Medium articles
│   │   ├── GitHubStats/     ← GitHub analytics
│   │   ├── Contact/         ← Contact form
│   │   └── Layout/          ← Navbar, Footer
│   ├── config/
│   │   └── portfolio.ts     ← ⭐ All your content here
│   ├── hooks/               ← Custom React hooks
│   ├── styles/              ← Global styles
│   └── App.tsx
├── public/
│   └── assets/              ← Images, icons
├── index.html
├── tailwind.config.ts
├── vite.config.ts
└── package.json
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| React 18 | UI framework |
| TypeScript | Type safety |
| Tailwind CSS | Styling |
| Vite | Build tool |
| Framer Motion | Animations |
| React Query | Data fetching |
| Lucide React | Icons |

---

## 🚢 Deployment

### Vercel (Recommended)

```bash
npm install -g vercel
vercel --prod
```

### Netlify

```bash
npm run build
# Drag & drop the `dist/` folder to Netlify
```

### GitHub Pages

```bash
npm run build
npm run deploy  # Uses gh-pages package
```

---

## 🎨 Customizing the Theme

The color palette is defined in `tailwind.config.ts`:

```typescript
colors: {
  github: {
    dark: '#0D1117',
    darker: '#161B22',
    border: '#30363D',
    muted: '#21262D',
  },
  accent: {
    blue: '#58A6FF',
    purple: '#7C3AED',
    green: '#3FB950',
    coral: '#F78166',
  },
  text: {
    primary: '#F0F6FC',
    secondary: '#C9D1D9',
    muted: '#8B949E',
  },
}
```

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">

**Built with ❤️ by [Suraj Kumar](https://github.com/surajj2024)**

[Medium](https://medium.com/@surajjkumar9608) · [LinkedIn](https://www.linkedin.com/in/suraj-kumar-5b34a61b3/) · [GitHub](https://github.com/surajj2024)

</div>
