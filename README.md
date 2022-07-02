# tex-template
Template repo for TeX document

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

Customize build directives by modifying [`latexmkrc`](latexmkrc) (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)
