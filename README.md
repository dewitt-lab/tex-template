# Template repository for a LaTeX project

<!---see here for how the relative links work: https://stackoverflow.com/questions/60193771/a-badge-in-github-template-repository-that-will-refer-to-clones-build-status-n--->
[![Build and Deploy](../../actions/workflows/build-deploy.yml/badge.svg)](../../actions/workflows/build-deploy.yml)


## Template contents
- TeX source file: [`main.tex`](main.tex)
- GitHub Pages document index: [`index.md`](index.md)
- Example bibtex file: [`references.bib`](references.bib)
- Example PDF figure: [`darwin-rock.pdf`](figures/darwin-rock.pdf)
- [`latexmkrc`](latexmkrc) file for optional customization of build directives (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)
- GitHub Actions workflow file (building and deploying PDFs): [`.github/workflows/build-deploy.yml`](.github/workflows/build-deploy.yml)

## PDF Deployment

### Configuring GitHub Pages

To enable GitHub Pages for your repository:

1. Go to the repository settings
2. Navigate to "Pages"
3. Select "GitHub Actions" as the source

Once enabled, your compiled PDFs will be available at `https://<username>.github.io/<repository>/`.

### Adding PDFs to GitHub Pages

> [!NOTE]
> It is not necessary to commit compiled PDF files from your local build.
> The [`.gitignore`](.gitignore) is set to ignore PDF files in the root directory.
> If you want to commit PDF files (i.e. for figures), put them in a subdirectory.

This template automatically compiles `.tex` files [`index.md`](index.md) to PDFs. You can simply:

1. Add your LaTeX files to the repository root
2. Update the [`index.md`](index.md) file to include links to the corresponding PDF files (e.g. `main.pdf` for `main.tex`)
3. Push changes to the main branch
4. PDFs will be available on GitHub Pages

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
