# Terminal Commands

This README lists useful terminal commands useful for django project. Commands assume macOS with bash and a local virtual environment.

## Git & Repo Management

- `git add .` — Stage all changes.
- `git commit -m "feat: add view"` — Commit staged changes.
- `git push --set-upstream origin master` — Push local `master` and set upstream.
- `git reset --hard origin/master` — Discard local commits and reset to remote.
- `git clean -fd` — Remove untracked files and directories.
- `git rm --cached my_project/__pycache__/*.pyc` — Stop tracking compiled cache files.
- `git ls-files | grep __pycache__` — List tracked cache files.

## Python Env & Django

- `source .venv/bin/activate` — Activate virtualenv (bash/zsh).
- `. .venv/bin/activate` — Activate virtualenv (POSIX shell shorthand).
- `deactivate` — Deactivate the current virtual environment.
- `python3 manage.py startapp about` — Create `about` app.
- `pip3 freeze --local > requirements.txt` — Export the current environment dependencies.
- `cat ./requirements.txt` — Display the contents of requirements.txt.
- `python3 manage.py runserver` — Start the development server.
- `django-admin version` — Display installed Django version.
- `pip3 list` — List all installed packages in the environment.

## Filesystem Operations

- `mv about aboutus` — Rename app folder from `about` to `aboutus`.
- `rm -rf aboutus` — Remove existing folder (use before re-running `startapp`, if needed).

## Notes

- `.gitignore` updated to include `__pycache__/` so cache folders are ignored globally.

## Troubleshooting

- If the Project Explorer shows changes in `__pycache__`, ensure the files aren’t tracked by git (see commands above) and that `.gitignore` includes `__pycache__/`.

## Setup & Run

Use these commands to set up and run the project locally on macOS with bash.

```bash
# 1) Create and activate virtual environment (if not already created)
python3 -m venv .venv
source .venv/bin/activate

# 2) Install dependencies
pip install -r requirements.txt

# 3) Apply migrations
python3 manage.py migrate

# 4) Run development server
python3 manage.py runserver

# Optional: Create superuser
python3 manage.py createsuperuser
```

## Common Django Workflow

Frequently used commands during development and maintenance.

```bash
# Create a new app
python3 manage.py startapp <app_name>

# Detect and create migrations from model changes
python3 manage.py makemigrations

# Apply migrations to the database
python3 manage.py migrate

# Run tests
python3 manage.py test

# Collect static files (for production)
python3 manage.py collectstatic

# Open Django shell
python3 manage.py shell

# Check for project issues
python3 manage.py check

# Run development server
python3 manage.py runserver

# Create superuser
python3 manage.py createsuperuser
```
