# Notes AI Assistant — One-File Reference (Notion + Google Drive + Local)
**Goal:** “ChatGPT on your notes” with citations, 100% local retrieval, optional cloud or local LLM.

## 1) Quick Start
```bash
python -V  # Python 3.10+
python -m venv .venv && source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
cp .env.example .env  # fill values
```

## 2) Put/Sync Your Notes
- Place files into `notes/` (subfolders ok). Supports .md, .txt, .pdf, .docx.
- Optional: Notion → set `NOTION_API_KEY`; Drive → set OAuth paths, then:
```bash
python notes_ai_assistant.py sync
```

## 3) Build Index
```bash
python notes_ai_assistant.py index
```

## 4) Chat (CLI)
```bash
python notes_ai_assistant.py chat
```

## 5) Web UI
```bash
python notes_ai_assistant.py ui
```
Open http://127.0.0.1:7860

## Tips
- To use local models with **Ollama**, set `USE_LOCAL=1` in `.env` and `ollama pull llama3`.
- Re-run `index` after adding or changing notes.
- Sources are shown with filenames and similarity scores.

## Privacy
- Retrieval runs locally in Chroma (on your disk).
- When using OpenAI, text is sent to the API to generate answers; use local Ollama for fully local flow.

