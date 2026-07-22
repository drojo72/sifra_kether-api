# Sifra Kether — API

Backend API for Sifra Kether. Serves the database, ingestion pipeline, search engine, and authentication.

## Stack

- Python / FastAPI
- Neon PostgreSQL
- pgvector, pg_trgm

## Setup

```bash
# Clone
git clone https://github.com/drojo72/sifra_kether-api.git
cd sifra_kether-api

# Environment
cp .env.example .env
# Edit .env with your Neon credentials

# Dependencies
pip install -r requirements.txt

# Database
psql $DATABASE_URL -f database/schema/sifra_kether_db_v1_beta.sql

# Run
uvicorn src.main:app --reload
```

## Structure

```
database/
  schema/           Canonical schema
  migrations/       Versioned migrations
  seeds/            Seed data
src/
  api/              REST endpoints
  ingest/           Pipeline logic
  search/           Full-text + vector search
  auth/             Authentication
  models/           Domain models
tests/
```

## API Documentation

Auto-generated at `/docs` (Swagger UI) and `/redoc` (ReDoc).

## License

Apache 2.0 — See [LICENSE](https://github.com/drojo72/sifra_kether/LICENSE)
