# n8n + AI automation templates

Production-minded n8n workflows for small businesses: AI that answers only from your own content, reads documents, and hands off to a person when it isn't sure. Every template imports into n8n as-is; credentials are left empty.

| Template | What it does | Stack |
|---|---|---|
| [AI support chatbot (RAG)](templates/ai-support-chatbot-rag-slack-sheets.json) | Website chat that answers from your own pages, hands off to Slack when the answer isn't there, logs every chat to Sheets | n8n AI Agent, Claude, OpenAI embeddings, Slack, Google Sheets |
| [PDF purchase orders → ERP CSV](templates/pdf-purchase-orders-to-erp-csv.json) | Reads emailed POs (scans, faxes, handwriting), validates customers, parts and prices against your data, writes one CSV per order and flags anything uncertain | IMAP, Claude (PDF input), Google Sheets/Drive, Slack |
| [Google Play review triage](templates/play-reviews-ai-triage-slack-sheets.json) | Classifies new reviews by severity, sends urgent ones to Slack, drafts replies, keeps a daily digest | Apify, Claude, Slack, Google Sheets |
| [Daily Play review alerts](templates/daily-play-review-alerts-to-slack.json) | Simple daily new-review alert | Apify, Slack |
| [Weekly hiring signals](templates/weekly-hiring-signals-to-slack.json) | Which target companies are hiring, posted to Slack weekly | Apify, Slack |

## Design rules used in every template
- **No guessing.** AI output is forced into a schema and checked against your data; anything unclear is flagged for a person.
- **No duplicates.** Re-runs and retried webhooks don't create second records.
- **No silent failures.** Errors and handoffs go to Slack.
- **Your accounts.** Everything runs in your n8n, with your keys.

## Demo
43-second walkthrough of the support chatbot: [media/kettle-hill-chatbot-demo.mp4](media/kettle-hill-chatbot-demo.mp4)

![PDF purchase order workflow](media/pdf-po-canvas.png)

![Support chatbot workflow](media/chatbot-canvas.png)

## Need one adapted to your business?
These are starting points. For a version wired into your own tools (CRM, ERP, help desk), get in touch through the profile links on this account.

License: MIT
