## Hi, I'm Max

AI engineer. I build LLM products that talk to real users: chatbots, agents, MCP servers, and the
evals that keep them honest. Most of my work is in Python, with some TypeScript.

### What I'm building now

**LLM assistant for a medical call center** · private repo · in production since February 2026

- A patient-facing bot in messengers and an assistant for call-center operators. Hard cases go to a
  human operator (human-in-the-loop).
- The model is self-hosted, so patient data never leaves the client's servers: Mistral Small 24B on
  Ollama, 4× RTX 4090. We started on Llama 3 and switched after comparing models on real queries and
  on speed.
- "LLM as a selector": the model picks an ID from a closed list and code renders the facts, so it
  can't invent a price or an instruction.
- Each turn goes through a 7-stage pipeline with 0–2 LLM calls, timeouts and a kill switch per layer.
  Daily snapshots keep the bot answering when the upstream system is down.
- A hermetic gate of 2,200+ tests (cut from 1 h to 4 min), counter-sweeps on live data, code review
  by subagents.
- Python, asyncio, PostgreSQL, Meilisearch, Docker, Telegram Bot API

### Public projects

- **[rag-mbti](https://github.com/Dafuqhappen/rag-mbti)** · Hybrid RAG (BM25 + embeddings, RRF)
  that lifted Recall@3 from 0.40 to 0.93, my own MCP server, and an agent loop written by hand in
  Python, then ported to TypeScript and LangGraph.
- **[tg-pushups-bot](https://github.com/Dafuqhappen/tg-pushups-bot)** · Telegram bot for a daily
  fitness challenge. Counts video notes, keeps streaks and posts a morning summary. Running since
  April 2026 in a chat of about 15 people.
- **[foodgram](https://github.com/Dafuqhappen/foodgram)** · Recipe and shopping-list service on
  Django REST Framework and PostgreSQL. Capstone of the Yandex Practicum Python course.
- **[kittygram_final](https://github.com/Dafuqhappen/kittygram_final)** · The same kind of Django
  app, deployed with Docker Compose, Nginx and CI/CD on GitHub Actions.

### Stack

**AI:** LLM applications, structured output, prompt engineering, RAG and hybrid search, offline
evaluation (Recall@k, MRR, regression sweeps), MCP, tool use, agents (hand-written and LangGraph),
local inference

**Models:** Mistral Small 3.2, Llama 3.1, 3.3 and 4 Scout, Qwen 3.5, Gemma 4, GPT-OSS 20B, GigaChat,
Claude

**Backend:** Python (asyncio, FastAPI, Django, DRF, pytest), TypeScript, PostgreSQL, Meilisearch,
Chroma, Docker, Nginx, GitHub Actions, Linux

**Daily tools:** Claude Code (subagents, skills, CLAUDE.md), Ollama, Git

### How I work

I measure before I believe. A prompt or model change ships after it holds up on real data, and
Claude Code writes most of the code from my specs while I own the architecture and the checks.

### Contact

[LinkedIn](https://www.linkedin.com/in/max-ten-94a850252) · [Telegram](https://t.me/tenmaxten)
