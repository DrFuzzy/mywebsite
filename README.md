# My Personal Website

This repository hosts my personal website at:

👉 **[https://drfuzzy.github.io/](https://drfuzzy.github.io/)**

The site is built with **Quarto** and published using **GitHub Pages**.

---

## Repository Structure

This repository uses a **single-repository, two-branch workflow**:

* **`quarto`** → source branch (this is where all edits are made)
* **`gh-pages`** → published output (served by GitHub Pages)

You only ever edit files on the `quarto` branch. The `gh-pages` branch is **fully managed by Quarto** and should not be edited manually.

---

## Editing & Publishing Workflow

This is the exact, working process to update the site.

### 1. Clone the repository and check out `quarto`

```bash
git clone https://github.com/DrFuzzy/DrFuzzy.github.io.git
cd DrFuzzy.github.io
git checkout quarto
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
git push origin quarto
```

### 4. Render and publish the site

```bash
quarto render --clean
quarto publish gh-pages
```

* `quarto render --clean` forces a full rebuild (recommended when BibTeX or JS-driven content changes)
* `quarto publish gh-pages` renders the site and publishes it to the `gh-pages` branch

After this step, the site is live at:

👉 **[https://drfuzzy.github.io/](https://drfuzzy.github.io/)**

---

## Important Notes

* You do **not** copy files manually between branches
* You do **not** commit `_site/` yourself
* Quarto automatically renders the site and commits the output to `gh-pages`
* GitHub Pages serves the `gh-pages` branch directly

---

## Alternative Rendering Branch: `revealjs`

This repository also contains an **experimental** branch named **`revealjs`**.

* The `revealjs` branch is **independent from Quarto**
* It uses **Reveal.js** directly to render content (e.g. presentations or an alternative site layout)
* It follows a **different build and deployment model** than the `quarto` branch

⚠️ **Status note:** The `revealjs` branch is **experimental** and **may be behind** the current Quarto-based site published from `gh-pages`. It should not be considered feature-complete or fully up to date.

To publish the site from `revealjs`, GitHub Pages would need to be configured to use:

* **Branch**: `revealjs`
* **Folder**: `/` (root)

This requires changing the GitHub Pages settings from `gh-pages` to `revealjs`.

> ⚠️ This setup has not been recently tested. Switching the active Pages branch to `revealjs` *should* work in principle, but may require additional adjustments depending on the contents of that branch.

In normal operation, the **canonical and supported workflow** is the Quarto-based pipeline using the **`quarto → gh-pages`** branches.

---

## Resources

This website makes use of the following technologies:

* **[Quarto](https://quarto.org)** – Open-source scientific and technical publishing system
* **[Bibtex-js](https://github.com/pcooksey/bibtex-js)** – Client-side BibTeX rendering
* **[Reveal.js](https://revealjs.com)** – HTML presentation framework (used in the experimental `revealjs` branch)

---

## Licence

This project is licensed under the MIT Licence. See the [LICENCE](LICENCE) file for details.
