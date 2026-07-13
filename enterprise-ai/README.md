<div align="center">

# 🏢 Enterprise AI

### Production-ready AI application template for enterprise systems

<br/>

![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

<br/>

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white)
![AWS Bedrock](https://img.shields.io/badge/AWS_Bedrock-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)

</div>

---

## 🌟 Overview

**Enterprise AI** is a production-ready template for building AI-powered enterprise applications. It combines a robust Laravel backend with a Python AI service layer, AWS cloud infrastructure, and a GraphQL API — all containerized with Docker and ready for multi-tenant SaaS deployment.

This template is battle-tested from real enterprise projects and includes everything you need to ship AI features to production.

---

## ✨ Features

### 🤖 AI Capabilities
- **RAG Pipeline** — Retrieval-Augmented Generation with vector search
- **AI Agents** — Autonomous agents with tool use and memory
- **LLM Integration** — AWS Bedrock (Claude), OpenAI, Gemini support
- **Embeddings** — Document embedding and semantic search
- **Streaming** — Real-time streaming AI responses via SSE

### ⚙️ Backend
- **Multi-Tenant SaaS** — Row-level security, tenant isolation
- **GraphQL API** — Type-safe, flexible API with subscriptions
- **Queue System** — Redis-backed async job processing
- **Event-Driven** — Domain events and event sourcing patterns
- **Clean Architecture** — Repository pattern, service layer, DTOs

### ☁️ Infrastructure
- **AWS Ready** — Lambda, Bedrock, S3, API Gateway, SQS
- **Docker** — Full containerization with docker-compose
- **CI/CD** — GitHub Actions pipeline included
- **Monitoring** — Structured logging, health checks, metrics

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     CLIENT LAYER                         │
│              Web App / Mobile / API Clients              │
└─────────────────────┬───────────────────────────────────┘
                      │
┌─────────────────────▼───────────────────────────────────┐
│                   API GATEWAY                            │
│              GraphQL + REST + WebSocket                  │
└──────┬──────────────┬──────────────────┬────────────────┘
       │              │                  │
┌──────▼──────┐ ┌─────▼──────┐ ┌────────▼───────┐
│   Laravel   │ │  Python AI │ │  Auth Service  │
│   Backend   │ │  Service   │ │  (JWT/OAuth)   │
└──────┬──────┘ └─────┬──────┘ └────────────────┘
       │              │
┌──────▼──────┐ ┌─────▼──────┐
│ PostgreSQL  │ │AWS Bedrock │
│  + pgvector │ │  (Claude)  │
└─────────────┘ └────────────┘
       │
┌──────▼──────┐
│    Redis    │
│  (Cache +   │
│   Queues)   │
└─────────────┘
```

---

## 🚀 Quick Start

### Prerequisites

- Docker & Docker Compose
- PHP 8.2+ (for local dev without Docker)
- Python 3.11+
- AWS account (for Bedrock)

### Installation

```bash
git clone https://github.com/surajj2024/enterprise-ai.git
cd enterprise-ai

# Copy environment files
cp .env.example .env
cp ai-service/.env.example ai-service/.env

# Start all services
docker-compose up -d

# Run migrations
docker-compose exec app php artisan migrate --seed

# Install AI service dependencies
docker-compose exec ai-service pip install -r requirements.txt
```

### Access the application

| Service | URL |
|---------|-----|
| GraphQL Playground | http://localhost:8000/graphql |
| API Documentation | http://localhost:8000/api/docs |
| AI Service | http://localhost:8001 |
| Redis Commander | http://localhost:8081 |

---

## 📁 Project Structure

```
enterprise-ai/
├── app/                         ← Laravel application
│   ├── Domain/                  ← Domain models & business logic
│   │   ├── AI/                  ← AI domain (agents, RAG, embeddings)
│   │   ├── Tenant/              ← Multi-tenancy
│   │   └── User/                ← User management
│   ├── Application/             ← Use cases & services
│   ├── Infrastructure/          ← Repositories, external services
│   └── Http/
│       └── GraphQL/             ← GraphQL resolvers & types
│
├── ai-service/                  ← Python AI microservice
│   ├── src/
│   │   ├── agents/              ← AI agent implementations
│   │   ├── rag/                 ← RAG pipeline
│   │   ├── embeddings/          ← Embedding service
│   │   └── llm/                 ← LLM client abstraction
│   └── requirements.txt
│
├── .github/
│   └── workflows/
│       ├── ci.yml               ← CI pipeline
│       └── deploy.yml           ← AWS deployment
│
├── docker-compose.yml
├── docker-compose.prod.yml
└── README.md
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend Framework | Laravel 11 |
| AI Service | Python 3.11 + FastAPI |
| API | GraphQL (Lighthouse) + REST |
| Database | PostgreSQL 16 + pgvector |
| Cache & Queue | Redis 7 |
| LLM | AWS Bedrock (Claude 3) |
| Embeddings | OpenAI / Bedrock Titan |
| Container | Docker + Docker Compose |
| Cloud | AWS (Lambda, S3, SQS, Bedrock) |
| CI/CD | GitHub Actions |

---

## 🔒 Multi-Tenant Security

```php
// Automatic tenant scoping — all queries are tenant-isolated
class UserRepository extends TenantAwareRepository
{
    public function findAll(): Collection
    {
        // Automatically adds WHERE tenant_id = current_tenant
        return User::query()->get();
    }
}
```

---

## 🤖 AI Agent Example

```python
# Create an AI agent with tools
agent = EnterpriseAgent(
    llm=BedrockClient(model="claude-3-sonnet"),
    tools=[
        DatabaseQueryTool(),
        DocumentSearchTool(),
        EmailSenderTool(),
    ],
    memory=ConversationMemory(max_tokens=4000)
)

response = await agent.run(
    "Summarize the Q3 sales report and email it to the team"
)
```

---

## 📊 GraphQL API Example

```graphql
# Query with AI-powered insights
query GetSalesInsights($tenantId: ID!, $quarter: String!) {
  salesInsights(tenantId: $tenantId, quarter: $quarter) {
    summary
    topProducts {
      name
      revenue
      trend
    }
    aiRecommendations {
      action
      priority
      reasoning
    }
  }
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
