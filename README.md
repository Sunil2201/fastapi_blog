# FastAPI Blog

A blog application built with FastAPI, async SQLAlchemy, and Jinja2 templates.

## Features

- REST API for posts and users (`/api/posts`, `/api/users`)
- Server-rendered pages with Jinja2 templates
- Async database access via SQLAlchemy + aiosqlite
- Auto-created SQLite database on startup

## Project Structure

```
fastapi_blog/
├── main.py          # App entry point, template routes, error handlers
├── database.py      # DB engine, session factory, get_db dependency
├── models.py        # SQLAlchemy ORM models (User, Post)
├── schemas.py       # Pydantic request/response schemas
├── routers/
│   ├── posts.py     # CRUD routes for /api/posts
│   └── users.py     # CRUD routes for /api/users
├── templates/       # Jinja2 HTML templates
├── static/          # CSS, JS, images
└── media/           # Uploaded profile pictures
```

## Setup

```bash
# Create and activate virtual environment
python -m venv .venv
.venv\Scripts\activate        # Windows
source .venv/bin/activate     # Linux/macOS

# Install dependencies
pip install -r requirements.txt

# Run the server
fastapi dev main.py
```

The database (`blog.db`) is created automatically on first run.

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/posts` | List all posts |
| POST | `/api/posts` | Create a post |
| GET | `/api/posts/{id}` | Get a post |
| PUT | `/api/posts/{id}` | Replace a post |
| PATCH | `/api/posts/{id}` | Partially update a post |
| DELETE | `/api/posts/{id}` | Delete a post |
| GET | `/api/users` | List all users |
| POST | `/api/users` | Create a user |
| GET | `/api/users/{id}` | Get a user |
| PATCH | `/api/users/{id}` | Update a user |
| DELETE | `/api/users/{id}` | Delete a user |

Interactive API docs available at `http://localhost:8000/docs`.

## Tech Stack

- [FastAPI](https://fastapi.tiangolo.com/)
- [SQLAlchemy](https://www.sqlalchemy.org/) (async)
- [aiosqlite](https://aiosqlite.omnilib.dev/)
- [Pydantic](https://docs.pydantic.dev/)
- [Jinja2](https://jinja.palletsprojects.com/)