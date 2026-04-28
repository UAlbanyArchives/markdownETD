# Markdown Template for thesis and dissertations

Use `template.md` to format your thesis and dissertation.

You can edit Markdown with any text editor, but specific editors also render as you write.
* [Typora](https://typora.io/) (paid)
* [marktext](https://github.com/marktext/marktext) (free)

Online/Browser-Based Editors
* [StackEdit](https://stackedit.io/)
* [Dillinger](https://dillinger.io/)

[Markdown Guide](https://www.markdownguide.org/)

## Pandoc command for converting to HTML

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

## Pandoc command for converting to PDF

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