# SmartTax – File Your Gains Taxes in Seconds

## Overview
SmartTax is a full-stack web app to upload Groww trade reports (CSV/JSON), compute short-term and long-term capital gains, view a tax summary, and ask a simple AI assistant tax questions.

- Frontend: React + Vite + React Router + Axios + Tailwind CSS
- Backend: Flask + Flask-CORS + Pandas + SQLite

## Project Structure
```
smart-tax/
├── frontend/
├── backend/
└── database/
```

## Prerequisites
- Node.js 18+
- Python 3.9+

## Backend Setup
```
cd smart-tax/backend
python -m venv .venv
# Windows PowerShell
. .venv/Scripts/Activate.ps1
pip install -r requirements.txt
python app.py
```
The backend starts on http://127.0.0.1:5000

## Frontend Setup
```
cd smart-tax/frontend
npm install
npm start
```
The frontend starts on http://127.0.0.1:5173 (Vite). If needed, change the API base URL in `src/services/api.js`.

## Environment
- Optional: set `OPENAI_API_KEY` for the assistant. If unset, a placeholder answer is returned.

## Notes
- SQLite DB file will be created in `database/smarttax.db` on first run.
- Supported uploads: CSV or JSON with columns/fields: `date`, `type` (BUY/SELL), `symbol`, `quantity`, `price`.
- Gains are computed using a simple FIFO cost basis and 365-day holding period for LTCG.
