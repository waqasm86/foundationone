# foundationone

GitHub Pages documentation hub for my projects.

- Live site: https://waqasm86.github.io/foundationone/
- Docs are built with **MkDocs + Material for MkDocs** and deployed via **GitHub Actions**.

## Local preview

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Open: http://127.0.0.1:8000/foundationone/

## Deploy

Push to `main`. The workflow at `.github/workflows/pages.yml` builds and deploys the site to GitHub Pages.

> In GitHub repo settings: **Settings → Pages → Build and deployment → Source = GitHub Actions**.
