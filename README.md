# Template repository for a $\LaTeX$ project

## Template contents
- $\TeX$ source file: [`main.tex`](main.tex)
- bibtex bibliography file: [`references.bib`](references.bib)
- [`latexmkrc`](latexmkrc) file for optional customization of build directives (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)

## Compilation with `latexmk`

### Build
Build [`main.pdf`](main.pdf) with
```bash
latexmk -pdf
```

### Clean
Clean auxiliary files with
```bash
latexmk -pdf -c
```

## Writing suggestions

### Semantic line breaks

While writing $\TeX$ source files, add a line break after each sentence (or clause).
This makes editing and collaborating on the text much easier, and it makes git diffs much more readable.
For more on this, see https://sembr.org.

### Initialed source comments

A low-key way to add comments or questions on the text is to put comments in the $\TeX$ source with your initials. This doesn't clutter up the compiled PDF. For example:
```tex
% WSD: I don't understand the result described below
```
