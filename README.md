# Template repository for a LaTeX project

<!---see here for how the relative links work: https://stackoverflow.com/questions/60193771/a-badge-in-github-template-repository-that-will-refer-to-clones-build-status-n--->
[![](../../actions/workflows/build-deploy.yml/badge.svg)](../../actions/workflows/build-deploy.yml)


## Template contents
- TeX source file: [`main.tex`](main.tex)
- Bibtex bibliography file: [`references.bib`](references.bib)
- Example PDF figure: [`darwin-rock.pdf`](figures/darwin-rock.pdf)
- [`latexmkrc`](latexmkrc) file for optional customization of build directives (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)
- GitHub Actions workflow file (testing PDF compilation): [`.github/workflows/build-deploy.yml`](.github/workflows/build-deploy.yml)

## Dependencies

 - TeX Live: [www.tug.org/texlive/]()

## PDF compilation

> [!NOTE]
> It is not necessary to commit compiled PDF files from your local build.
> The [`.gitignore`](.gitignore) is set to ignore PDF files in the root directory.
> If you want to commit PDF files (i.e. for figures), put them in a subdirectory.

### Testing

A GitHub Action, triggered by push, automatically compiles PDFs and publishes to GitHub Pages.
The PDF can be accessed as an artifact of each action run.
Click the badge icon at the top of this README to access these runs.
If TeX compilation errors occur, the badge will reflect this, and the author of the breaking changes will receive an email.

### Local PDF compilation with `latexmk`

#### Build

Build with
```bash
latexmk -pdf
```

#### Clean

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
