# Curriculum-Vitae

Resume of Murat Ambarkutuk, written in LaTeX.

| File | What it is |
|---|---|
| `Ambarkutuk_Resume.tex` | The content. Comments mark metric slots (`% METRIC:`) and restore notes for removed items. |
| `Ambarkutuk_Resume.sty` | Layout, plus the custom list macros (`\resumeItem`, `\resumeNestedListStart`/`End` for child bullets). |
| `refs.bib` | Publications. The printed order follows the `\nocite` lines at the top of the `.tex` (newest first). |
| `Ambarkutuk_Resume.pdf` | The built output (2 pages). Rebuild it after any change to the files above. |

## Build

```bash
latexmk -pdf Ambarkutuk_Resume.tex
```

Needs a TeX Live install with `fontawesome5`, `marvosym`, `natbib` and `enumitem` (on Debian or Ubuntu:
`texlive-latex-extra texlive-fonts-extra texlive-bibtex-extra`).

## Conventions

- Present-tense bullets are the parents; past-tense deliverables are nested under them as children.
- No phone number or home address on purpose: the resume is published on a public website.
