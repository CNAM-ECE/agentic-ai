# Session Notes — Agentic AI: Complete Course for Beginners

One note per chapter of [the freeCodeCamp video](https://www.youtube.com/watch?v=Zy7EXDONlTY) (Boktiar Ahmed Bappy, ~24 h). Each note links to the timestamp, the matching code in [`src/`](../../src/), and any diagram or slides.

| # | Session | Video | Code |
|---|---|---|---|
| **Phase 1 · Foundations** | | | |
| 00 | [Introduction & Planning](00-introduction-and-planning.md) | [0:00:00](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=0s) | — |
| 01 | [Evolution from LLMs to Agentic AI](01-evolution-from-llms-to-agentic-ai.md) | [0:08:33](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=513s) | — |
| 02 | [Agentic AI: Core Characteristics & Components](02-agentic-ai-characteristics-and-components.md) | [0:41:26](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=2486s) | — |
| **Phase 2 · Python for agents** | | | |
| 03 | [Asynchronous Programming for AI Agents](03-asynchronous-programming.md) | [1:33:18](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=5598s) | [`01-async-programming`](../../src/01-async-programming/) |
| 04 | [Pydantic Data Validation](04-pydantic-data-validation.md) | [2:06:23](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=7583s) | [`02-pydantic`](../../src/02-pydantic/) |
| **Phase 3 · LangChain agents** | | | |
| 05 | [Single AI Agent with LangChain](05-langchain-single-agent.md) | [3:27:08](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=12428s) | [`03-langchain-single-agent`](../../src/03-langchain-single-agent/) |
| 06 | [Multi-Agent System with LangChain](06-langchain-multi-agent.md) | [4:49:37](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=17377s) | [`04-langchain-multi-agent`](../../src/04-langchain-multi-agent/) |
| **Phase 4 · LangGraph** | | | |
| 07 | [What is LangGraph? LangChain vs LangGraph](07-langchain-vs-langgraph.md) | [6:30:27](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=23427s) | — |
| 08 | [LangGraph Core Components](08-langgraph-core-components.md) | [7:44:43](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=27883s) | — |
| 09 | [Sequential Workflows](09-sequential-workflows.md) | [8:29:07](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=30547s) | [`05-langgraph-workflows`](../../src/05-langgraph-workflows/) 1–3 |
| 10 | [Parallel Workflows](10-parallel-workflows.md) | [9:19:04](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=33544s) | 4–5 |
| 11 | [Conditional Workflows](11-conditional-workflows.md) | [10:15:27](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=36927s) | 6–7 |
| 12 | [Iterative Workflows](12-iterative-workflows.md) | [11:06:05](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=39965s) | 8 |
| 13 | [First Agentic Chatbot](13-first-agentic-chatbot.md) | [11:35:51](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=41751s) | [`06-agentic-chatbot`](../../src/06-agentic-chatbot/) |
| **Phase 5 · Memory, tools, monitoring** | | | |
| 14 | [Why Persistence is Required](14-persistence.md) | [12:43:49](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=45829s) | `05-…/9_Persistence` |
| 15 | [Streaming Responses](15-streaming-responses.md) | [13:51:00](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=49860s) | `app_simple.py` |
| 16 | [Chat Threading](16-chat-threading.md) | [14:10:02](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=51002s) | `app_thread.py` |
| 17 | [Permanent Persistence with a Database](17-database-persistence.md) | [14:42:02](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=52922s) | `app_db.py` |
| 18 | [Monitoring with LangSmith](18-langsmith-monitoring.md) | [15:16:31](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=54991s) | `app_db.py` |
| 19 | [Tool Integration](19-tool-integration.md) | [15:40:24](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=56424s) | `app_tool.py` |
| 20 | [RAG in the Chatbot](20-rag-in-chatbot.md) | [16:54:17](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=60857s) | `app_rag.py` |
| 21 | [Human-in-the-Loop](21-human-in-the-loop.md) | [17:50:27](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=64227s) | `app_hitl.py` |
| **Phase 6 · Deployment** | | | |
| 22 | [CI/CD on AWS with Docker & GitHub Actions](22-cicd-deployment-aws.md) | [18:48:09](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=67689s) | external repo |
| 23 | [Deploy on Render for Free](23-deployment-render.md) | [19:52:05](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=71525s) | external repo |
| **Phase 7 · Projects** | | | |
| 24 | [BappyGPT: your own ChatGPT agent](24-project-bappygpt.md) | [20:06:27](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=72387s) | external repo |
| 25 | [TripMate AI: multi-agent travel planner](25-project-tripmate-ai.md) | [22:21:17](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=80477s) | external repo |

## Note template

Every note follows the same shape:

```markdown
# NN · Title
> **Video:** [hh:mm:ss](link&t=…) · **Code:** [src/…](…) · **Diagram / Slides:** …

## Overview / Why          ← the problem in 1–2 paragraphs + a mermaid diagram
## Lesson 01 · …            ← one section per step taught, with the code that matters
> [!NOTE] / [!TIP] / [!IMPORTANT] / [!WARNING]
## References               ← [n] description. Available in [Title](url)
```
