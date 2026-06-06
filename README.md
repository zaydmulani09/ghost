# ghost

> A local AI that runs entirely in your browser. No install. No API key. No GPU. No data leaves your device.

![ghost model picker](https://raw.githubusercontent.com/zaydmulani09/ghost/main/screenshot.png)

## try it

**[ghost.zaydmulani09.github.io](https://zaydmulani09.github.io/ghost/ghost.html)**

Open the link. Pick a model. Chat. That's it.

## how it works

ghost runs a quantized LLM entirely in WebAssembly inside your browser tab.

- **Inference:** [wllama](https://github.com/ngxson/wllama) — WebAssembly binding for llama.cpp
- **Models:** GGUF quantized models loaded from HuggingFace
- **Caching:** Models download once and cache in your browser's Cache API — works offline after first load
- **RAG:** Drag a `.txt` or `.pdf` onto the chat — ghost embeds and retrieves relevant chunks locally
- **Voice:** Web Speech API — speak your message, no mic data leaves your device

## models

| Model | Size | Speed | Best for |
|-------|------|-------|----------|
| Qwen2.5 1.5B | 1.1 GB | ~3 tok/s | General use, coding |
| Qwen2 0.5B | 400 MB | ~8 tok/s | Quick answers, low RAM |
| TinyLlama 1.1B | 670 MB | ~5 tok/s | Lightweight devices |

## features

- **Fully offline** after first model download
- **Model picker** — choose speed vs quality
- **Markdown rendering** — code blocks, lists, bold, italic
- **RAG** — chat with your own documents (.txt, .pdf)
- **Voice input** — mic button, auto-sends on silence
- **Multi-turn memory** — remembers conversation context
- **Copy button** on every response
- **PWA installable** — add to home screen

## stack

- Pure vanilla JS ES modules — no build step, no npm
- wllama 2.3.7 (MIT) for WASM inference
- PDF.js 4.0.379 for PDF text extraction
- Web Speech API for voice
- Single HTML file + service worker

## local dev

```bash
node server.js
# open http://localhost:8000/ghost.html
```

Requires Node.js. The server sends COOP/COEP headers required for multi-thread WASM.

## license

MIT

