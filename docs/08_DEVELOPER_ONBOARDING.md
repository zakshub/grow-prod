# Developer Onboarding

## 1. Repository roles

- Source of truth: https://github.com/zakshub/grow
- Production workspace: https://github.com/zakshub/grow-prod

Do not commit new work to the source of truth without explicit owner approval. New production implementation and all new assets belong in the production workspace.

## 2. Verified source stack

- Python 3.13 or newer.
- Django 5.2.
- PostgreSQL driver psycopg.
- SQLite for zero service local development and tests.
- pytest and pytest-django.
- Ruff for formatting and linting.
- mypy with Django stubs.
- GitHub Actions with PostgreSQL 18 service for CI.

Redis and Dramatiq are not current dependencies.

## 3. Local setup

The source repository documents this Windows oriented setup. Adapt paths for Linux or macOS without changing project assumptions.

1. Install Python 3.13 or newer.
2. Clone the source repository for read only inspection or a separately approved development branch.
3. Create a virtual environment.
4. Install the project with development extras.
5. Run migrations.
6. Load only synthetic fixtures.
7. Run the full test suite.

Commands documented by the source repository:

- python -m venv .venv
- .\.venv\Scripts\python.exe -m pip install -e .[dev]
- .\.venv\Scripts\python.exe manage.py migrate
- .\.venv\Scripts\python.exe manage.py load_synthetic_fixtures
- .\.venv\Scripts\python.exe manage.py load_synthetic_assessment_pack
- .\.venv\Scripts\python.exe manage.py load_synthetic_career_pack
- .\.venv\Scripts\python.exe -m pytest

For Linux and macOS, use the environment's Python executable path and shell syntax. Do not commit local databases or environment files.

## 4. Environment configuration

The source includes .env.example. Local development defaults to SQLite. PostgreSQL is selected through DATABASE_ENGINE and POSTGRES_DB, POSTGRES_USER, POSTGRES_PASSWORD, POSTGRES_HOST and POSTGRES_PORT.

Production requires DJANGO_SECRET_KEY when DEBUG is false. Never commit credentials, production secrets or real participant data.

## 5. Quality gates

Run before every handoff:

- Ruff formatter check.
- Ruff lint.
- mypy.
- Django system checks.
- Migration drift check.
- Fresh migrations.
- Synthetic fixture loaders.
- Full pytest suite.
- PostgreSQL CI.

A local SQLite pass does not prove PostgreSQL concurrency or deployment behaviour.

## 6. Contribution workflow

1. Confirm the task and requirement IDs.
2. Read the relevant product and technical documents.
3. Check current source implementation before adding new models or services.
4. Create a focused branch in grow-prod for new production work.
5. Record any conflict with source requirements in the decision register.
6. Implement behind domain services and explicit contracts.
7. Add migrations and tests.
8. Update documentation and implementation status.
9. Run all quality gates.
10. Submit a reviewable pull request with test evidence and known limitations.

## 7. Coding boundaries

- Preserve modular monolith unless an evidence based reason supports a change.
- Do not add Redis, Dramatiq, APIs, AI or speech just because they appear in future architecture notes.
- Do not implement a production dashboard using Django Admin.
- Do not put direct identifiers in participant model fields or logs without an approved design.
- Do not mutate published assessment or career versions in place.
- Do not overwrite evidence or contradictions.
- Do not use real participant data in development.
- Do not treat synthetic assessment or career content as validated.
- Do not expose raw provider prompts or credentials in frontend code.

## 8. Definition of Done

A developer task is complete only when:
- Requirement and acceptance criteria are met.
- Code and tests are committed.
- Migration state is clean.
- CI passes.
- Security and privacy implications are reviewed.
- Documentation matches the implementation.
- New decisions are recorded.
- Limitations and follow up work are visible.
- Owner approval is obtained where product or policy changes are involved.
