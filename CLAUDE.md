# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a [Quarto book](https://quarto.org/docs/books/) — *Data Science Team Training* — authored by Stephen D. Turner. It is reference material for the CSTE DSTT program covering version control, data organization, AI tools, dashboards, environments, project management, and other topics for public health data scientists.

This book will not cover technical topics that are covered in detail elsewhere (e.g., how to manipulate and analyze data with dplyr, how to make plots with ggplot2). The focus is more on things upstream or downstream of the technical implementation, less of a focus on code itself.

## Build & Preview

```sh
quarto render          # Build the book to _book/
quarto preview         # Live-preview in browser (auto-rebuilds on save)
```

Open `_book/index.html` to view the compiled output. The `_book/` directory is git-ignored.

## Publish

```sh
quarto publish gh-pages   # Publish to GitHub Pages (commits must be on main first)
```

The site publishes to <https://dstt.stephenturner.us/> from the `gh-pages` branch.

## Book Structure

Chapters and appendices are declared in `_quarto.yml`. To add content:

- Create a `.qmd` file and add it under the appropriate `part` in `_quarto.yml`
- Top-level headings should include a section label: `# My Chapter {#sec-my-chapter}`
- Cross-reference with `[Chapter -@sec-my-chapter]`
- Unnumbered chapters use `{.unnumbered}` (see `index.qmd`)
- Appendices go under the `appendices:` key in `_quarto.yml`

## Exercises

Each chapter that contains exercises must reset the counter at the top:

```r
#| echo: false
options(digits=3)
options(max.print=200)
.ex <- 1
```

Exercises use Quarto callout boxes with inline R to auto-number:

```
::: {.callout-note}
# Exercise `r .ex``r .ex=.ex+1`
...
:::
```

## References

Bibliography is in `references.bib`. Cite with `@key` or `[@key]`. The compiled references appear in `references.qmd`.
