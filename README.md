# Template repository for a $\LaTeX$ document

## Compilation with [`latexmk`](https://mg.readthedocs.io/latexmk.html)

### Build
```bash
latexmk -pdf
```
will produce [`main.pdf`](main.pdf)

### Clean
```bash
latexmk -pdf -c
```

## Configuration

Customize build directives by modifying the [`latexmkrc`](latexmkrc) file (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)

## Writing suggestions

### Semantic line breaks

While writing $\TeX$ source files add a line break after each sentence (or clause).
This makes editing and collaborating on the text much easier, and it makes git diffs much more readable.
For more on this, see https://sembr.org.

### Initialed source comments

A low-key way to add comments or questions on the text is to put comments in the $\TeX$ source with your initials. This doesn't clutter up the compiled PDF. For example:
```tex
% WSD: I don't understand the result described below
```
