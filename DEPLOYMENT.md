# Deployment Guidelines

## Production Backend

```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Configure environment
export DATABASE_URL="postgresql://user:password@localhost:5432/extractor_db"
export SECRET_KEY="<strong-random-secret>"
export DEBUG=false

# Run via Gunicorn
gunicorn app.main:app -w 2 -k uvicorn.workers.UvicornWorker -b 0.0.0.0:8000
```

## Frontend Build

```bash
cd frontend
npm ci
npm run build   # output in frontend/dist/
```

Serve `frontend/dist/` from your CDN or web server, and proxy `/api/*` to the backend.

## Checklists

- [ ] Set a strong `SECRET_KEY`
- [ ] Use an HTTPS connection string for the database
- [ ] Restrict `CORS_ORIGINS` to production domains
- [ ] Set `DEBUG=false` and `LOG_LEVEL=info`
- [ ] Pin all dependency versions before release
