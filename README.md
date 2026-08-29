# Biola Engineering Capstone — Project Ideas site

A small [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) site that:

1. **Embeds the Google proposal form** on the *Submit a Proposal* page
   (`docs/submit.md`), with the form's questions also listed as a fallback.
2. Gives every capstone idea its own page with four consistent sections —
   **Capstone Project Idea**, **Sponsor**, **Scholarship**, **Deliverables** —
   under `docs/ideas/`.

The form links here so all the evolving ideas live in one place instead of a
separate form submission per idea.

## Run locally

```bash
pip install -r requirements.txt
mkdocs serve
```

Open <http://127.0.0.1:8000>. `python -m mkdocs serve` also works if `mkdocs`
isn't on your PATH.

## Add an idea

1. Copy `docs/ideas/_template.md` → `docs/ideas/idea-NN-short-name.md`.
2. Fill in the four sections and set the status
   (`draft` / `exploring` / `sponsored` / `parked`).
3. Add a card in `docs/ideas/index.md`.
4. Add a nav line in `mkdocs.yml` under **Project Ideas**.
5. Commit and push.

## Deploy to GitHub Pages

Repo: <https://github.com/Biola-X/capstone> · Published site:
<https://biola-x.github.io/capstone/>

`.github/workflows/deploy.yml` runs `mkdocs gh-deploy` on every push to `main`,
which builds the site and force-pushes it to the `gh-pages` branch.

One-time setup after the first successful workflow run: in
**Settings → Pages**, set **Source: Deploy from a branch**, branch `gh-pages`,
folder `/ (root)`.

To deploy manually instead: `python -m mkdocs gh-deploy --force` from your
machine while authenticated to GitHub.

## Brand colors

Defined in `docs/stylesheets/biola.css` from
[biola.edu/brand](https://www.biola.edu/brand/toolkits-standards/visual-design):
Biola Red `#CC1122`, Electric Red `#FF342E`, Grad Blue `#1D273B`,
Sky Blue `#E2EFF8`, Fountain Blue `#0488A4`.
