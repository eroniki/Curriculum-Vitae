# Curriculum-Vitae

Resume of Murat Ambarkutuk, written in LaTeX.

| File | What it is |
|---|---|
| `Ambarkutuk_Resume.tex` | The content. Comments mark metric slots (`% METRIC:`) and restore notes for removed items. |
| `Ambarkutuk_Resume.sty` | Layout, plus the custom list macros (`\resumeItem`, `\resumeNestedListStart`/`End` for child bullets). |
| `refs.bib` | Publications. The printed order follows the `\nocite` lines at the top of the `.tex` (newest first). |
| `metrics.tex` | The numbers behind the bullets: one commented `\setmetric` line per slot, with the measurement protocol. |
| `Ambarkutuk_Resume.pdf` | The built output (2 pages). Rebuild it after any change to the files above. |
| `drafts/Ambarkutuk_Resume_metrics-draft.pdf` | Worksheet: every unmeasured number shows as a red `[key]` placeholder. Never publish it. |

## Build

```bash
latexmk -pdf Ambarkutuk_Resume.tex
```

Needs a TeX Live install with `fontawesome5`, `marvosym`, `natbib` and `enumitem` (on Debian or Ubuntu:
`texlive-latex-extra texlive-fonts-extra texlive-bibtex-extra`).

## Adding measured numbers

Bullets carry optional number clauses (`\M{keys}{clause}` in the `.tex`). Fill a slot in `metrics.tex`
(`\setmetric{amort-sep-ms}{41}`) and rebuild: a clause appears only when all of its numbers are set, so an
unmeasured slot can never leak into the published PDF. Tested with dummy values at five fill levels, from no
slots to all 27, it stays on 2 pages (the skills block moves to page 2 as a whole when page 1 fills up), and the build prints a loud
warning if a later edit pushes it past 2 pages. To regenerate the worksheet with red placeholders:

```bash
latexmk -pdf -usepretex -pretex='\def\METRICSDRAFT{1}' -jobname=Ambarkutuk_Resume_metrics-draft Ambarkutuk_Resume.tex
mkdir -p drafts && mv Ambarkutuk_Resume_metrics-draft.pdf drafts/
```

## Conventions

- Present-tense bullets are the parents; past-tense deliverables are nested under them as children.
- No phone number or home address on purpose: the resume is published on a public website.
- Teammates are not named, for the same reason.
- Every experience bullet stays at two lines or fewer.
