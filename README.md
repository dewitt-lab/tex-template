# Template repository for a LaTeX writing project

<!---see here for how the relative links work: https://stackoverflow.com/questions/60193771/a-badge-in-github-template-repository-that-will-refer-to-clones-build-status-n--->
[![Build and Deploy](../../actions/workflows/build-deploy.yml/badge.svg)](../../actions/workflows/build-deploy.yml)
[![View PDFs](https://img.shields.io/badge/View-PDFs-blue?logo=github)](../../deployments/github-pages)


This repo contains a LaTeX writing project.
Documents are automatically compiled upon each new commit and PDFs are served via a GitHub Pages site.
After setting up GitHub Pages (see [below](#enable-github-pages)),
your documents will be built and served at `https://<username>.github.io/<repository>/`.


## Contents

### Writing

- TeX source: [`main.tex`](main.tex)
- Bibtex references: [`references.bib`](references.bib)
- Figure directory: [`figures/`](figures/)

> [!NOTE]
> There's no need to commit compiled PDF files from your local build.
> PDF files in the root directory are ignored by git.

### Configuration

- [`_config.yml`](_config.yml): optionally specify which documents to serve on GitHub Pages.
By default, all `.tex` files in the repository root will be compiled and listed on the index page.
Override this like so (note: no `.pdf` or `.tex` extension):
  ```yaml
  documents:
    - main
    - supplementary
  ```
- [`latexmkrc`](latexmkrc): optional customization of TeX build directives (see [`latexmk` docs](https://mg.readthedocs.io/latexmk.html)).


## Enable GitHub Pages

To enable GitHub Pages for a new repository using this template:

1. Go to the repository settings
2. Navigate to "Pages"
3. Select "GitHub Actions" as the source
4. Back on the main repository page, click the gear icon ⚙️ on the right to edit the "About" section and check the box for "Use your GitHub Pages website".


## Dependencies

 - TeX Live: [www.tug.org/texlive/]()


## Local PDF compilation with `latexmk`

### Build

Build with
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

While writing TeX source files, add a line break after each sentence (or clause).
This makes editing and collaborating on the text much easier, and it makes git diffs much more readable.
For more on this, see https://sembr.org.

### Initialed source comments

A low-key way to add comments or questions on the text is to put comments in the TeX source with your initials. This doesn't clutter up the compiled PDF. For example:
```tex
% WSD: I don't understand the sentence below
A confusing sentence
```
