![title](/frontend/src/assets/title.png)

**Future Updates**

- Allow users to login so the data is persistent
- Allow users to enter multiple arXiv papers and then select which ones they want to query from
- Chunks stores in Postgres database keyed on user ID and paper ID


## About

ArXtract is a research intelligence engine that transforms any arXiv paper into structured, queryable insights. It evaluates a paper’s relevance to your research interests, highlights its most important contributions, searches for related work, and lets you interrogate the paper.

**Try it out at:** [arxtract-cxc.vercel.app](https://arxtract-cxc.vercel.app)

---
![Key Features](/frontend/src/assets/key_features.png)

## What It Does

As input, ArXtract expects an arXiv link and the user's research interests.

* **Key Sections:** Extracts title, problem statement, contribution, architecture, datasets, metrics, baselines, results, limitations into structured fields.
* **Relevance Scoring:** By entering your research topic, you get a 0–100 relevance score with the papers abtract and the top 5 most relevant text chunks.
* **Related Papers:** Discovers and ranks similar papers from arXiv based on your research interest by cosine similarity.
* **Research Query:** Ask follow-up questions about the paper and get context-constrained answers.

![System FlowChart](/frontend/src/assets/flowchart.png)

## Tech Stack

| Layer | Tech |
|-------|------|
| Frontend | React, TypeScript, Vite |
| Backend | Python FastAPI |
| LLM | OpenAI GPT-o4 |

## Project Structure

```
ArXtract/
├── backend/
│   ├── requirements.txt
│   └── app/
│       ├── main.py                         # FastAPI app & endpoints
│       ├── config.py                       # Model & parameter settings
│       ├── schemas.py                      # Pydantic request/response models
│       └── services/
│           ├── arxiv_client.py             # PDF fetching, parsing, chunking
│           ├── llm_client.py               # GPT calls (extraction, reranking, chat)
│           └── similarity.py               # Embeddings & cosine similarity
├── frontend/
│   ├── index.html
│   ├── package.json
│   ├── vite.config.ts
│   └── src/
│       ├── main.tsx                        # Entry point
│       ├── App.tsx                         # Main app, tab routing
│       ├── App.css                         # Global styles
│       ├── index.css                       # Base styles
│       └── components/
│           ├── NavBar.tsx                  # Top navigation bar
│           ├── NavBar.css
│           ├── AnimatedTitle.tsx           # Landing page title animation
│           ├── AnimatedTitle.css
│           ├── FeatureCard.tsx             # Animated feature cards
│           ├── FeatureCard.css
│           ├── ParticlesPanel.tsx          # Particle background
│           ├── CustomCursor.tsx            # Custom cursor effect
│           ├── TabBar.css                  # Tab styling
│           ├── ShellFieldDisplay.tsx       # Terminal-style metadata fields
│           ├── AbstractScoreGauge.tsx      # Circular relevance gauge
│           ├── ChunkBarChart.tsx           # Top chunks bar chart
│           ├── RelatedPapersChart.tsx      # Related papers ranking chart
│           ├── ChatPanel.tsx               # Research Q&A chat interface
│           └── ModelFlowchart.tsx          # Interactive pipeline diagram
└── README.md
```

Built for 2026 CxC Hackathon