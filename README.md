# Markdown Template for thesis and dissertations

Use `template.md` to format your thesis and dissertation.

[Markdown Guide](https://www.markdownguide.org/)

## Pandoc command for HTML

```
pandoc template.md
  --to=html5 \
  --standalone \
  --citeproc \
  --bibliography=references.bib \
  --csl=styles\chicago-notes-bibliography-17th-edition.csl \
  -o thesis.html
```

### With Math

```
pandoc template.md \
  --to=html5 \
  --standalone \
  --mathml \
  --citeproc \
  --bibliography=references.bib \
  --csl=styles\chicago-notes-bibliography-17th-edition.csl \
  -o thesis.html
```

## Pandoc command for PDF

```
pandoc template.md \
  --pdf-engine=xelatex \
  --citeproc \
  --bibliography=references.bib \
  --csl=styles\chicago-notes-bibliography-17th-edition.csl \
  -o thesis.pdf
```

### To get a tagged PDF with lualatex

Convert to LaTeX
```
pandoc template.md \
  -o thesis.tex \
  --standalone \
  --to=latex \
  --citeproc \
  --bibliography=references.bib \
  --csl=styles\chicago-notes-bibliography-17th-edition.csl
```

Add to the top of the .tex
```
\DocumentMetadata{
  lang=en,
  pdfstandard=ua-2,
  tagging=on
}
```

Convert to PDF
```
lualatex thesis.tex
```