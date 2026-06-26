# harvest
Data ingestion and enrichment pipeline for Alloy. Pulls, normalizes, tags, and embeds works across games, anime, film, books, music, and more.

## What it does

-- Connectors for IGDB, AniList, TMDB, VNDB, OpenLibrary, MusicBrainz
-- Normalizes heterogenous API responses to a shared schema
-- LLM-assisted taxonomy tagging (mood, themes, aesthetic)
-- Cross-medium semantic embeddings via sentence-transformers
-- Scheduled sync via Celery Beat

## Stack

celery[gevent]==5.x    task queue
redis                  broker + rate limiter + result backend
asyncpg                raw async postgres driver
pydantic v2            data models and validation (10x faster than v1)
httpx                  async HTTP client
tenacity               retry logic (cleaner than celery's built-in)
sentence-transformers  embeddings
anthropic              LLM tagging (Haiku)
ruff                   linting + formatting (replaces black + flake8 + isort)
mypy                   type checking
pytest + pytest-asyncio testing
typer                  CLI
python-dotenv          env management

## License

AGPL v3.
