## Newspaper Web App (Django) — Project Description

**Main Functionalities**
- User authentication (login, logout, registration, custom user model)
- Article CRUD (Create, Read, Update, Delete) operations
- Comments on articles (add, view; only logged-in users)
- List and detail views for articles
- Admin interface for managing articles and comments
- Permissions: Only authors can edit or delete their own articles
- Responsive Bootstrap 5 UI
- Home and static pages

**Technologies Used**
- Python 3, Django 5
- Django apps: `accounts`, `articles`, `pages`
- Third-party: crispy-forms (`crispy_forms`, `crispy_bootstrap5`), whitenoise for static files
- Bootstrap 5 (CDN) for frontend styling
- Database: Configurable via `DATABASE_URL` (default: PostgreSQL recommended)
- Environment variable management via `environs`
- Gunicorn WSGI server (for production)
- Heroku-ready settings (allowed hosts, static files, trusted origins)

**Deployment & Setup**
- Clone the repo and install requirements (`pip install -r requirements.txt`)
- Set environment variables: `SECRET_KEY`, `DATABASE_URL`, `DEBUG`, etc. (see `.env.example`)
- Run migrations: `python manage.py migrate`
- Collect static files: `python manage.py collectstatic`
- Create superuser: `python manage.py createsuperuser`
- Start local server: `python manage.py runserver`
- For production: Deploy to Heroku (Procfile and Whitenoise are ready)
  - Set up PostgreSQL add-on on Heroku
  - Configure environment variables in Heroku dashboard
  - App entry: `web: gunicorn django_project.wsgi --log-file -` (see `Procfile`)
- Static files handled by Whitenoise and Django's staticfiles system

**Other Notes**
- Default login redirect: Home page
- Email backend: Console (for development)
- Timezone: Africa/Tunis
- CSRF trusted origins: `.herokuapp.com`

---
