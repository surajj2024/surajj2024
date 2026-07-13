<div align="center">

# 🗄️ Text-to-SQL

### Convert natural language into optimized, secure SQL using LLMs

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/AWS_Bedrock-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)

</div>

---

## 🌟 Overview

**Text-to-SQL** is an intelligent query assistant that translates natural language questions into optimized, secure SQL queries. It uses schema-aware prompting, vector similarity search for context retrieval, and multi-tenant security to ensure users only access their own data.

```
"Show me the top 10 customers by revenue this quarter"
                        ↓
SELECT c.name, SUM(o.total) as revenue
FROM customers c
JOIN orders o ON c.id = o.customer_id
WHERE o.created_at >= DATE_TRUNC('quarter', NOW())
GROUP BY c.id, c.name
ORDER BY revenue DESC
LIMIT 10;
```

---

## ✨ Features

- 🧠 **Schema-Aware Prompting** — Automatically injects relevant table schemas into context
- 🔒 **Multi-Tenant Security** — Row-level security ensures data isolation
- ✅ **SQL Validation** — Validates and sanitizes generated SQL before execution
- 💬 **Conversational Interface** — Maintains conversation history for follow-up queries
- 🔍 **Vector Similarity Search** — Retrieves relevant schema context using embeddings
- ⚡ **Query Optimization** — Suggests indexes and query improvements
- 📊 **Result Formatting** — Returns results in JSON, CSV, or table format
- 🔄 **Multi-LLM Support** — AWS Bedrock (Claude), OpenAI, Gemini

---

## 🏗️ Architecture

```
User Query (Natural Language)
         │
         ▼
   Schema Embedding Store
   (Vector Similarity Search)
         │
         ▼
   Context Assembly
   (Relevant tables + columns)
         │
         ▼
   LLM Prompt Construction
   (Schema + Query + History)
         │
         ▼
   AWS Bedrock / Claude
         │
         ▼
   SQL Validation & Sanitization
         │
         ▼
   Security Check (Tenant Isolation)
         │
         ▼
   Query Execution → Results
         │
         ▼
   Natural Language Response
```

---

## 🚀 Quick Start

### Prerequisites

- Python 3.11+
- PostgreSQL 14+
- AWS account (for Bedrock) or OpenAI API key

### Installation

```bash
git clone https://github.com/surajj2024/text-to-sql.git
cd text-to-sql

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy environment variables
cp .env.example .env
```

### Configuration

```env
# .env
DATABASE_URL=postgresql://user:password@localhost:5432/mydb
AWS_REGION=us-east-1
AWS_BEDROCK_MODEL=anthropic.claude-3-sonnet-20240229-v1:0
OPENAI_API_KEY=sk-...          # Optional: OpenAI fallback
EMBEDDING_MODEL=text-embedding-3-small
MAX_SCHEMA_TOKENS=4000
ENABLE_QUERY_VALIDATION=true
```

### Run the API

```bash
uvicorn src.main:app --reload --port 8000
```

### Try it out

```bash
curl -X POST http://localhost:8000/query \
  -H "Content-Type: application/json" \
  -d '{
    "question": "How many users signed up last month?",
    "tenant_id": "org_123"
  }'
```

---

## 📁 Project Structure

```
text-to-sql/
├── src/
│   ├── main.py              ← FastAPI application
│   ├── query_engine.py      ← Core Text-to-SQL logic
│   ├── schema_store.py      ← Schema embedding & retrieval
│   ├── llm_client.py        ← LLM abstraction (Bedrock/OpenAI)
│   ├── sql_validator.py     ← SQL validation & sanitization
│   ├── security.py          ← Multi-tenant security layer
│   └── conversation.py      ← Conversation history management
├── prompts/
│   └── text_to_sql.txt      ← Prompt template
├── migrations/              ← Database migrations
├── tests/
├── docker-compose.yml
├── requirements.txt
└── README.md
```

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python 3.11+ |
| API Framework | FastAPI |
| LLM | AWS Bedrock (Claude 3) |
| Database | PostgreSQL |
| Embeddings | OpenAI text-embedding-3-small |
| Vector Store | pgvector |
| Validation | sqlparse + custom rules |
| Containerization | Docker |

---

## 🔒 Security Features

- **SQL Injection Prevention** — Parameterized queries only, no raw string interpolation
- **Tenant Isolation** — Automatic `WHERE tenant_id = ?` injection
- **Query Allowlist** — Only `SELECT` statements allowed by default
- **Rate Limiting** — Per-user query rate limits
- **Audit Logging** — All queries logged with user context

---

## 📊 API Reference

### `POST /query`

```json
{
  "question": "Show top 5 products by sales",
  "tenant_id": "org_123",
  "conversation_id": "conv_456",  // optional: for follow-ups
  "format": "json"                // json | csv | table
}
```

**Response:**
```json
{
  "sql": "SELECT p.name, SUM(s.amount) as total_sales FROM ...",
  "results": [...],
  "explanation": "I found the top 5 products ranked by total sales amount.",
  "execution_time_ms": 42
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
