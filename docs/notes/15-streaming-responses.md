# 15 · Streaming Responses in Agentic Chatbot with LangGraph

> **Video:** [13:51:00](https://www.youtube.com/watch?v=Zy7EXDONlTY&t=49860s) · **Code:** [`test.py`](../../src/06-agentic-chatbot/test.py) (terminal) · [`app_simple.py`](../../src/06-agentic-chatbot/app_simple.py) (Streamlit) · compare [`non_stream.py`](../../src/06-agentic-chatbot/non_stream.py)

> [!IMPORTANT]
> **Streaming** means the model sends tokens **as soon as they are generated**, instead of waiting for the full response. LLMs generate token by token anyway. `invoke()` waits for the last token; `stream()` hands each one over immediately.

## Why it matters

| Benefit | Why |
|---|---|
| Faster perceived response, **lower drop-off** | Users leave apps that sit silent for 30–60 s |
| Human-like conversation | Builds trust and keeps users engaged (compare a voice assistant that replies after a minute) |
| Multimodal UIs | Show progress while an image or other output is being produced |
| Long outputs (code, blogs) | The reader starts before generation ends |
| **Cancel midway, save tokens** | Providers bill per output token, so stopping early costs less |
| Interleaved UI updates | Show "thinking…", tool calls and tool results as they happen, so the app does not look frozen |

---

## Lesson 01 · `invoke` vs `stream` in the terminal

```python
from agentic_chatbot_backend import chatbot
from langchain_core.messages import HumanMessage

CONFIG = {"configurable": {"thread_id": "thread-1"}}

# blocking: wait for the whole answer
chatbot.invoke({"messages": [HumanMessage(content="Generate a blog about Python")]}, config=CONFIG)

# streaming: a generator of (chunk, metadata) pairs
for message_chunk, metadata in chatbot.stream(
        {"messages": [HumanMessage(content="Generate a blog about Machine learning")]},
        config=CONFIG,
        stream_mode="messages"):
    if message_chunk.content:
        print(message_chunk.content, end="", flush=True)
```

| `stream_mode` | Yields |
|---|---|
| `"values"` | Full state after each super-step |
| `"updates"` | Only the delta each node returned |
| **`"messages"`** | **LLM tokens** as `(AIMessageChunk, metadata)`, used for chat UIs |
| `"custom"` | Anything a node emits via the stream writer |

> [!TIP]
> `chatbot.stream(...)` returns a **generator**. Printing it shows `<generator object …>`, so iterate over it. `end=""` + `flush=True` keeps tokens on one line and prints them immediately.

## Lesson 02 · Streaming in Streamlit

```python
with st.chat_message("assistant"):
    ai_message = st.write_stream(                          # renders chunks live, returns full text
        message_chunk.content
        for message_chunk, metadata in chatbot.stream(
            {"messages": [HumanMessage(content=user_input)]},
            config=CONFIG,
            stream_mode="messages",
        )
    )

st.session_state["message_history"].append({"role": "assistant", "content": ai_message})
```

`st.write_stream` consumes the generator, paints tokens as they arrive, and **returns the concatenated string**, which is then saved to `session_state`.

> [!NOTE]
> Once tools are added ([19](19-tool-integration.md)), `stream_mode="messages"` also yields `ToolMessage` chunks. Filter with `if isinstance(message_chunk, AIMessage)` so raw tool output does not reach the chat bubble ([`app_thread.py`](../../src/06-agentic-chatbot/app_thread.py) already does this).

## References

[1] Stream modes. Available in [LangGraph — Streaming](https://langchain-ai.github.io/langgraph/concepts/streaming/)

[2] `st.write_stream`. Available in [Streamlit API](https://docs.streamlit.io/develop/api-reference/write-magic/st.write_stream)
