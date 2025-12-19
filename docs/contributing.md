# Contributing

## Quick edits

1. Open the page you want to change.
2. Click the **Edit** (pencil) icon in the top-right.
3. Create a pull request.

## Local preview

Prereqs: Python + pip.

```bash
git clone https://github.com/waqasm86/foundationone.git
cd foundationone

python -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
mkdocs serve
```

Open http://127.0.0.1:8000/foundationone/ (note the `/foundationone/` prefix).

## Adding a new project

Create a folder under `docs/projects/<project-name>/` and add it to `nav:` in `mkdocs.yml`.
