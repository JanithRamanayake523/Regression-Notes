# Math 3330: Regression Notes

A static Quarto book rebuilding the MATH 3330 course notes
(originally at https://12ramsake.github.io/MATH-3330/).

This is a plain static site — no interactive widgets or animations.

## Structure

- `_quarto.yml` — book configuration (chapters, theme, TOC, numbering)
- `index.qmd` — Preface
- `Unit_1.qmd` — Review material
- `Unit_1_files/` — figures used in Unit 1
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

1. Create `Unit_N.qmd` at the project root.
2. Add its filename to the `chapters:` list in `_quarto.yml`.
3. Put any figures it uses in `Unit_N_files/`.
4. Re-render.
