# Template repository for a LaTeX project

<!---see here for how the relative links work: https://stackoverflow.com/questions/60193771/a-badge-in-github-template-repository-that-will-refer-to-clones-build-status-n--->
[![Build and Deploy](../../actions/workflows/build-deploy.yml/badge.svg)](../../actions/workflows/build-deploy.yml)


## Template contents
- TeX source file: [`main.tex`](main.tex)
- Configuration file: [`_config.yml`](_config.yml)
- Bibtex bibliography file: [`references.bib`](references.bib)
- Example PDF figure: [`darwin-rock.pdf`](figures/darwin-rock.pdf)
- [`latexmkrc`](latexmkrc) file for optional customization of build directives (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)
- GitHub Actions workflow file (testing PDF compilation): [`.github/workflows/build-deploy.yml`](.github/workflows/build-deploy.yml)

## Configuration

The [`_config.yml`](_config.yml) file allows you to specify which LaTeX documents to publish to GitHub Pages:

```yaml
documents:
  - main
  - chapter1
  - appendix
```

If you have multiple LaTeX documents in your repository, add them to the `documents` list in `_config.yml` (without the `.tex` extension). These documents will be:

1. Compiled to PDF
2. Listed on the GitHub Pages site
3. Available for download

If you don't specify any documents in `_config.yml`, all `.tex` files in the root directory will be compiled by default.

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

### GitHub Pages Deployment

This template includes automatic deployment to GitHub Pages. When you push to the main branch, the documents specified in [`_config.yml`](_config.yml) will be compiled and their PDFs will be deployed to GitHub Pages with a simple directory listing.

To enable GitHub Pages for your repository:

1. Go to the repository settings
2. Navigate to "Pages"
3. Select "GitHub Actions" as the source

Once enabled, your compiled PDFs will be available at `https://<username>.github.io/<repository>/`.

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
