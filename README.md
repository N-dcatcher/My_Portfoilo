# AI-Powered Support Email Dashboard

## Features

- Fetches and filters support/query/request/help emails from mailbox.
- Extracts sender, subject, body, date, phone, summary.
- Sentiment analysis and priority scoring.
- Contextual draft replies using company knowledge base (RAG/LLM).
- Editable reply, simulate send, mark resolved.
- Dashboard: Email list, details, analytics panel.

## Architecture

![Architecture Diagram](docs/architecture.png)

```
[Email Provider (IMAP)] -> [FastAPI Backend + SQLite + FAISS] <-> [React Dashboard]
```

## Quickstart

### Environment variables

Set these in `.env` or your shell:

```
IMAP_HOST=imap.gmail.com
IMAP_USER=your@email.com
IMAP_PASS=yourpassword
OPENAI_KEY=sk-xxxx
```

### Backend

```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

### Frontend

```bash
cd frontend
npm install
npm start
```

## Demo Steps

1. Run backend and frontend.
2. Click "Fetch Emails" (or auto-fetch).
3. View urgent/support emails in dashboard.
4. See extracted info, sentiment, priority.
5. Generate/edit reply, click "Send" (simulated).
6. View analytics panel (urgent/pending counts).

## Limitations & Future Work

- Only simulates email sending.
- Sentiment/priority: rule-based (improve with ML).
- RAG uses prompt template, replace with OpenAI API for full demo.
- Add multi-lingual, thread context, admin canned replies if time permits.

## Demo Video

[Demo Video Link](https://your-demo-link)

## License

MIT
