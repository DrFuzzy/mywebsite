# My Personal Website

This repository contains the source code and publishing setup for my personal website.

The site is built with **Quarto** and published using **GitHub Pages**.

---

## Repository Structure

This repository uses a **single-repository, two-branch workflow**:

* **`main`** → source branch (this is where all edits are made)
* **`gh-pages`** → published output (served by GitHub Pages)

You only ever edit files on the `main` branch. The `gh-pages` branch is **fully managed by Quarto** and should not be edited manually.

---

## Editing & Publishing Workflow

This is the exact, working process to update the site.

### 1. Clone the repository and check out `main`

```bash
git clone https://github.com/DrFuzzy/mywebsite.git
cd mywebsite
git checkout main
```

### 2. Make content changes

Edit any Quarto source files, for example:

* `about.qmd`
* `publications.qmd`
* `bibtex/publications.bib`
* other `.qmd`, `.css`, or asset files

### 3. Commit and push your changes

```bash
git add .
git commit -m "Update site content"
git push origin main
```

### 4. Render and publish the site

```bash
quarto render --clean
quarto publish gh-pages
```

* `quarto render --clean` forces a full rebuild (recommended when BibTeX or JS-driven content changes)
* `quarto publish gh-pages` renders the site and publishes it to the `gh-pages` branch

After this step, the published site is updated.

---

## Important Notes

* You do **not** copy files manually between branches
* You do **not** commit `_site/` yourself
* Quarto automatically renders the site and commits the output to `gh-pages`
* GitHub Pages serves the `gh-pages` branch directly

---

## Resources

* **[Quarto](https://quarto.org)** – Open-source scientific and technical publishing system
* **[Bibtex-js](https://github.com/pcooksey/bibtex-js)** – Client-side BibTeX rendering

---

## Licence

This project is licensed under the MIT Licence. See the [LICENCE](LICENCE) file for details.
