# Meridian Corp AI Data Assistant

A browser-based AI data assistant that simulates a real enterprise data environment. Students log in and ask business questions in plain English against 10 enterprise systems for a fictional $500M B2B industrial supplies distributor.

## The Simulation

Meridian Corp is a $500M B2B industrial supplies distributor with three operating divisions:

- **Industrial Division** (~$250M): Salesforce CRM, NetSuite Finance, SAP Operations
- **Energy Division** (~$150M): Legacy CRM, QuickBooks Finance, Oracle SCM
- **Safety Division** (~$100M): HubSpot CRM, shared NetSuite Finance
- **Corporate HQ**: Workday HR, NetSuite Consolidation, Zendesk Support

41 tables, 26,000+ rows, 3 years of data (2023–2025).

## Stack

- **Backend**: FastAPI + Claude Sonnet + DuckDB
- **Auth**: JWT login, per-user spending limits
- **Agent**: Claude with `query_database` and `code_execution` tools
- **Frontend**: HTML/CSS/JS chat interface with SSE streaming

## Setup

```bash
cp .env.example .env
# Edit .env with your Anthropic API key
pip install -r requirements.txt
python scripts/generate_meridian.py
python scripts/create_admin.py
uvicorn app.main:app --reload
```
