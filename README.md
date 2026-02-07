# Todo App

A simple Django todo list app with a flashy glassmorphism UI.

## Local Development

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `DJANGO_SECRET_KEY` | Secret key for production | dev key |
| `DJANGO_DEBUG` | Enable debug mode | `False` |
| `DJANGO_ALLOWED_HOSTS` | Comma-separated hosts | `*` |
| `DJANGO_CSRF_TRUSTED_ORIGINS` | Comma-separated origins | none |

## Production

Uses gunicorn and whitenoise for static files:

```bash
python manage.py collectstatic --noinput
python manage.py migrate --noinput
gunicorn config.wsgi:application --bind 0.0.0.0:8000
```
