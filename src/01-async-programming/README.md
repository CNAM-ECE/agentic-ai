# 01 · Asynchronous Programming

> **Notes:** [03 · Asynchronous Programming for AI Agents](../../docs/notes/03-asynchronous-programming.md) · **Slides:** [`docs/slides/03-asynchronous-programming.pdf`](../../docs/slides/03-asynchronous-programming.pdf)

Why every agent framework (LangGraph, AutoGen, CrewAI) is async underneath: I/O-bound work such as LLM calls, search and scraping overlaps instead of queueing.

| File | What it shows |
|---|---|
| [`asynchronous.ipynb`](asynchronous.ipynb) | `fetch_weather` (4 s) + `fetch_news` (2 s): **≈6 s** sequential with `time.sleep` vs **≈4 s** with `async def` / `await asyncio.sleep` / `asyncio.gather` |

```bash
# standard library only, any Python 3.11 kernel
jupyter notebook asynchronous.ipynb
```

> [!NOTE]
> The notebook uses top-level `await main()`, which works inside Jupyter. In a `.py` script use `asyncio.run(main())`.
