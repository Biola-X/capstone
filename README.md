# Biola-X site

An [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) site for
**Biola-X**, Biola University Engineering's umbrella initiative for
industry-connected work. Three sections, shown as tabs under the header:

| Section | Folder | What it holds |
| --- | --- | --- |
| **Engineering Senior Capstone** | `docs/capstone/` | Live catalog of project ideas + the embedded Google proposal form |
| **Summer Engineering Internships** | `docs/sei/` | Archive of completed SEI projects |
| **Industry Partnerships** | `docs/partnerships/` | One page per partner organization |

The Biola-X landing page is `docs/index.md`.

## Run locally

```bash
pip install -r requirements.txt
python -m mkdocs serve
```

Opens at <http://127.0.0.1:8000/capstone/> (the `/capstone/` path comes from
`site_url`). Live-reloads on save; `Ctrl+C` to stop.

## Add content

**A capstone idea** — copy `docs/capstone/ideas/_template.md` to
`docs/capstone/ideas/idea-NN-name.md`, fill the four sections (Capstone Project
Idea / Sponsor / Scholarship / Deliverables), set the status pill, then add a
card in `docs/capstone/ideas/index.md` and a nav line in `mkdocs.yml`.

**A completed SEI project** — copy a card block in `docs/sei/index.md`.

**A partner** — copy any file in `docs/partnerships/` (all use the same
four-card layout), add a card in `docs/partnerships/index.md` and a nav line in
`mkdocs.yml`.

Status pill classes (in `docs/stylesheets/biola.css`): `draft`, `exploring`,
`sponsored`, `parked`, `completed`, `active`, `prospective`, `paused`.

## Deploy to GitHub Pages

Repo: <https://github.com/Biola-X/capstone> · Published site:
<https://biola-x.github.io/capstone/>

`.github/workflows/deploy.yml` runs `mkdocs gh-deploy` on every push to `main`,
which builds the site and force-pushes it to the `gh-pages` branch.

One-time setup after the first successful workflow run: **Settings → Pages**,
**Source: Deploy from a branch**, branch `gh-pages`, folder `/ (root)`.

Manual deploy: `python -m mkdocs gh-deploy --force` while authenticated to GitHub.

## Brand colors

From [biola.edu/brand](https://www.biola.edu/brand/toolkits-standards/visual-design):
Biola Red `#CC1122`, Electric Red `#FF342E`, Grad Blue `#1D273B`,
Sky Blue `#E2EFF8`, Fountain Blue `#0488A4`.
