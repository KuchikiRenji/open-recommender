# Open Recommender — Open Source AI Recommendation System for Videos & Articles

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

<p align="center">
  <img src="https://raw.githubusercontent.com/KuchikiRenji/open-recommender/main/img/logo.webp" alt="Open Recommender - AI powered recommendation system" width="200" height="200">
</p>

<p align="center">
  <strong>Open Recommender</strong> is an open source, AI-powered recommendation engine that discovers videos and articles tailored to your interests using LLMs and your engagement data.
</p>

---

## What is Open Recommender?

**Open Recommender** is a self-hosted, open source recommendation system that uses large language models (LLMs) to recommend YouTube videos and web articles. It learns from your Twitter/X engagement (likes, retweets), builds a profile, generates search queries, and surfaces high-quality, timeless content—including niche content that’s hard to find—with a bias toward learning over pure entertainment.

Ideal for developers, researchers, and learners who want personalized content discovery without relying on closed algorithms.

---

## Features

- **Interest-based profiling** — Infers your interests from Twitter/X engagement (likes, retweets, etc.) and other data sources  
- **LLM-powered search** — Generates and runs search queries from your profile to find relevant videos and articles  
- **Video clip recommendations** — Recommends specific sections of videos, not just full videos  
- **Timeless over trending** — Prioritizes lasting, educational content over short-lived trends  
- **Niche discovery** — Surfaces “niche bangers”: high-quality content that’s difficult to find elsewhere  
- **Learning-first** — Tuned for learning and growth rather than pure entertainment  
- **Self-hosted & open source** — Full control over data and logic; no vendor lock-in  

---

## Tech Stack

- **Backend:** Node.js, tRPC, Prisma, Python (workers)  
- **Frontend:** React, TypeScript  
- **AI/LLM:** Modelfusion, LangChain, OpenAI-compatible APIs  
- **Data:** Twitter/X (optional), YouTube (via yt-dlp), web search  

---

## Quick Start

### Prerequisites

- Node.js (with Yarn)
- Python 3
- (Optional) Twitter/X account for interest profiling

### Installation

```bash
git clone https://github.com/KuchikiRenji/open-recommender.git
cd open-recommender
yarn && yarn build
python3 -m venv env
source env/bin/activate   # On Windows: env\Scripts\activate
pip install -r requirements.txt
```

In `packages/client`, `packages/server`, and `packages/cli`, copy env templates and fill in your values:

```bash
cp .env.example .env
# Edit each .env with your API keys and config
```

**Optional — Twitter as input:** Create an `accounts.txt` in the project root with credentials in the format:  
`username:password:email:email_password`

### Run the stack

```bash
yarn server    # Backend API
yarn client    # Frontend (e.g. http://localhost:5173)
yarn worker    # Background recommendation pipeline
```

1. Open the web client and log in (top right).  
2. After Twitter login, a recommendations pipeline run is triggered automatically.  
3. Monitor runs at: `http://localhost:5173/#/admin` (set `ADMIN="YourTwitterUsername"` in server `.env`).  
4. View your recommendation feed when the run finishes.

---

## How It Works

1. **Profile** — Downloads your Twitter data (tweets, likes, retweets) and recursively summarizes it into a user profile.  
2. **Queries** — Uses your profile to generate search queries.  
3. **Search** — Finds videos and articles from the web based on those queries.  
4. **Chunking** — Downloads transcripts and articles and splits them into “clips.”  
5. **Recommendation** — Ranks and recommends the best clips, grouped into mini learning playlists.

---

## References & Further Reading

- [Building an LLM-Powered Open Source Recommendation System for YouTube](https://dev.to/experilearning/building-an-llm-powered-open-source-recommendation-system-40fg)  
- [Create a system that borrows from Shorts, TikTok and incremental reading](https://experimentallearning.substack.com/p/from-spaced-repetition-systems-to)  
- [BookGPT: A General Framework for Book Recommendation Based on a Large Language Model](https://arxiv.org/pdf/2305.15673.pdf)  
- [A Survey on Large Language Models for Recommendation](https://arxiv.org/abs/2305.19860)  
- [Recommender Systems in the Era of Large Language Models (LLMs)](https://arxiv.org/abs/2307.02046)  

---

## Author & Contact

**KuchikiRenji**

- **GitHub:** [github.com/KuchikiRenji](https://github.com/KuchikiRenji)  
- **Email:** [KuchikiRenji@outlook.com](mailto:KuchikiRenji@outlook.com)  
- **Discord:** `kuchiki_renji`  

---

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

*Open Recommender — open source AI recommendation system for YouTube videos and articles | LLM-powered | Self-hosted | KuchikiRenji*
