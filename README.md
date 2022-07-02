# Template repository for a $\mathrm{\LaTeX}$ project

## Template contents
- $\mathrm{\TeX}$ source file: [`main.tex`](main.tex)
- bibtex bibliography file: [`references.bib`](references.bib)
- example PDF figure [`darwin-rock.pdf`](darwin-rock.pdf)
- [`latexmkrc`](latexmkrc) file for optional customization of build directives (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)

## Dependencies

 - $\mathrm{\TeX\ Live}$: www.tug.org/texlive/

## Compilation with `latexmk`

### Build
Build [`main.pdf`](main.pdf) with
```bash
latexmk -pdf
```

### Clean
Auxiliary build files will be ignored by `git`, but you can clean them locally with
```bash
latexmk -pdf -c
```

## Helpful writing conventions

### Semantic line breaks

While writing $\mathrm{\TeX}$ source files, add a line break after each sentence (or clause).
This makes editing and collaborating on the text much easier, and it makes git diffs much more readable.
For more on this, see https://sembr.org.

### Initialed source comments

A low-key way to add comments or questions on the text is to put comments in the $\mathrm{\TeX}$ source with your initials. This doesn't clutter up the compiled PDF. For example:
```tex
% WSD: I don't understand the sentence below
A confusing sentence
```
