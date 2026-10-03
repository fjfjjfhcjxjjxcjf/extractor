# Extract Project

A Python FastAPI backend with React/Vite frontend for data extraction tasks.

## Architecture

```
extractor/
├── backend/            # FastAPI application
│   ├── app/            # Application source code
│   │   ├── main.py     # Entry point
│   │   └── database.py # SQLAlchemy config
│   ├── requirements.txt
│   └── .env.example
└── frontend/           # React/Vite application
    ├── src/            # Source code
    ├── package.json
    └── vite.config.ts
```

## Prerequisites

- Python 3.11+
- Node.js 20+
- Git

## Setup

### Backend

```bash
cd backend
python -m venv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows
pip install -r requirements.txt
cp .env.example .env      # Edit with your values
uvicorn app.main:app --reload
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

## Local Execution

- Backend: http://localhost:8000
- Frontend: http://localhost:5173
- API docs: http://localhost:8000/docs

## Deployment

See [DEPLOYMENT.md](DEPLOYMENT.md) for deployment guidelines.
