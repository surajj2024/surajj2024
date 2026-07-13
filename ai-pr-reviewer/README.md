<div align="center">

# 🤖 AI Pull Request Reviewer

### Automated AI-powered code review using LLMs — integrated with GitHub Actions

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI_Compatible-412991?style=for-the-badge&logo=openai&logoColor=white)

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)
[![Medium Article](https://img.shields.io/badge/Read_on-Medium-000000?style=flat-square&logo=medium)](https://medium.com/@surajjkumar9608/i-built-an-ai-that-reviews-my-pull-requests-d9a591255e75)

</div>

---

## 🌟 Overview

**AI PR Reviewer** automatically reviews your pull requests using Large Language Models (LLMs). It integrates seamlessly into your GitHub Actions CI/CD pipeline and posts detailed review comments directly on your PRs — covering code quality, security vulnerabilities, performance issues, and best practices.

> 📖 Read the full story: [I Built an AI That Reviews My Pull Requests](https://medium.com/@surajjkumar9608/i-built-an-ai-that-reviews-my-pull-requests-d9a591255e75)

---

## ✨ Features

- 🔍 **Automated Code Review** — Reviews every PR automatically on open/update
- 🛡️ **Security Analysis** — Detects common vulnerabilities (SQL injection, XSS, etc.)
- ⚡ **Performance Suggestions** — Identifies N+1 queries, inefficient loops, memory leaks
- 📐 **Best Practices** — Enforces coding standards and design patterns
- 🎯 **Configurable Severity** — Filter by `critical`, `warning`, or `info` level
- 💬 **Inline Comments** — Posts comments directly on the relevant lines
- 🔄 **Multi-LLM Support** — Works with Gemini, GPT-4, Claude, and more
- ✍️ **AI Commit Messages** — Generates meaningful commit messages automatically

---

## 🏗️ Architecture

```
Pull Request Opened/Updated
         │
         ▼
  GitHub Actions Trigger
         │
         ▼
   Fetch PR Diff (GitHub API)
         │
         ▼
   Chunk & Prepare Context
         │
         ▼
   LLM Analysis (Gemini/GPT-4)
         │
         ▼
   Parse Review Response
         │
         ▼
   Post Inline Comments (GitHub API)
         │
         ▼
   Summary Comment on PR
```

---

## 🚀 Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/surajj2024/ai-pr-reviewer.git
cd ai-pr-reviewer
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up secrets in your target repository

```
GEMINI_API_KEY    → Your Google Gemini API key
GITHUB_TOKEN      → Auto-provided by GitHub Actions
```

### 4. Add the workflow to your project

Copy `.github/workflows/ai-review.yml` to your target repository.

### 5. Open a Pull Request

The AI reviewer will automatically trigger and post comments! 🎉

---

## ⚙️ Configuration

```yaml
# .github/workflows/ai-review.yml
- name: AI PR Review
  uses: surajj2024/ai-pr-reviewer@main
  with:
    gemini_api_key: ${{ secrets.GEMINI_API_KEY }}
    severity_threshold: warning    # critical | warning | info
    max_files: 20                  # Max files to review per PR
    language: auto                 # auto-detect or specify: python, php, js
    post_summary: true             # Post a summary comment
    inline_comments: true          # Post inline line comments
```

---

## 📁 Project Structure

```
ai-pr-reviewer/
├── src/
│   ├── reviewer.py          ← Core review logic
│   ├── github_client.py     ← GitHub API integration
│   ├── llm_client.py        ← LLM abstraction layer
│   ├── diff_parser.py       ← PR diff parsing
│   └── comment_formatter.py ← Review comment formatting
├── prompts/
│   ├── review_prompt.txt    ← Main review prompt template
│   └── commit_prompt.txt    ← Commit message prompt
├── .github/
│   └── workflows/
│       └── ai-review.yml    ← GitHub Actions workflow
├── tests/
├── requirements.txt
└── README.md
```

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python 3.11+ |
| LLM | Google Gemini Pro / GPT-4 |
| CI/CD | GitHub Actions |
| API | GitHub REST API v3 |
| Parsing | `unidiff` library |

---

## 📝 Example Review Output

```
🤖 AI Code Review Summary
━━━━━━━━━━━━━━━━━━━━━━━━

📊 Files reviewed: 5
🔴 Critical issues: 1
🟡 Warnings: 3
🔵 Suggestions: 7

Critical Issues:
  ⚠️  src/auth.py:42 — Potential SQL injection vulnerability
      Raw user input passed directly to query string.
      Fix: Use parameterized queries or ORM.

Warnings:
  ⚡ src/users.py:87 — N+1 query detected in loop
  📐 src/api.py:23  — Missing input validation
  🔒 src/config.py:5 — Hardcoded credentials detected
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
