# AI Agent Instructions for this Repository

## What this project is
- A small Django 6.0.6 todo application using SQLite.
- Uses Python 3.12 in CI and a local `venv` is present in the workspace.
- The main app is `todo`; project settings live under `config/`.

## Primary workflows
- Run tests: `python manage.py test`
- Install dependencies: `pip install -r requirements.txt`
- Linting in CI: `flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics`
- Additional flake8 command in CI: `flake8 . --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics`

## Key files and behavior
- `manage.py`: Django CLI entrypoint.
- `config/settings.py`: Django settings, including `LANGUAGE_CODE = 'ja'` and `TIME_ZONE = 'Asia/Tokyo'`.
- `config/urls.py`: routes root URL `/` to `todo.views.index`.
- `todo/models.py`: defines the `Task` model and `Task.is_overdue()`.
- `todo/views.py`: `index()` handles GET and POST for creating tasks and ordering by `posted_at` or `due_at`.
- `todo/tests.py`: existing unit tests for model behavior and the index view.
- `todo/templates/todo/index.html`: main template for the todo page.
- `.github/workflows/django.yml`: CI workflow for Python setup, dependency install, lint, and tests.

## Agent guidance
- Prefer small, targeted changes; this repository is a simple Django exercise app.
- Preserve Django conventions and avoid introducing unrelated architecture or external services.
- Keep the app compatible with Python 3.12 and Django 6.0.6.
- If adding features, update tests and ensure the current CI commands keep passing.
- Do not modify `db.sqlite3` unless the task explicitly involves database state or migrations.

## Notes
- There is no existing README or custom contribution docs in this repo.
- Use this file as the primary AI guidance for working on repository code and tests.
