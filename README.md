# Math 3330: Regression Notes

A static Quarto book rebuilding the MATH 3330 course notes
(originally at https://12ramsake.github.io/MATH-3330/).

This is a plain static site — no interactive widgets or animations.

## Structure

- `_quarto.yml` — book configuration (chapters/parts, theme, TOC, numbering)
- `index.qmd` — Preface
- `Unit_1_1.qmd` … `Unit_1_4.qmd` — the **Review material** part, split into
  one page per sub-topic (random variables, intro statistics, matrices and
  linear algebra, random vectors)
- `Unit_1_files/` — figures used by the Review material pages
- `old notes/` — the original scraped site, kept for reference while
  the new notes are rebuilt unit by unit
- `_book/` — generated static HTML output (not tracked in git; rebuild
  with the command below)

## Building the site

Requires [Quarto](https://quarto.org/) (RStudio ships a bundled copy at
`C:\Program Files\RStudio\resources\app\bin\quarto\bin\quarto.exe` if
it's not on your PATH).

```bash
quarto render
```

Output goes to `_book/`. Open `_book/index.html` in a browser to view it.

## Live preview while editing

```bash
quarto preview
```

Starts a local server and reloads automatically when a `.qmd` file changes.

## Adding a new unit

1. Create `Unit_N.qmd` (or split it into `Unit_N_1.qmd`, `Unit_N_2.qmd`, ...
   for sub-topics, one page each) at the project root.
2. Add the filename(s) to the `chapters:` list in `_quarto.yml`. Group
   related pages under a `part:` entry (see the "Review material" part)
   to get a nested, expandable section in the sidebar.
3. Put any figures it uses in `Unit_N_files/`.
4. Re-render.

## Publishing to GitHub Pages

```bash
quarto publish gh-pages
```

Builds the site and pushes it to the `gh-pages` branch. Run this again
after any content changes to redeploy.
