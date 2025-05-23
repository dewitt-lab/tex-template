# Template repository for a LaTeX project

<!---see here for how the relative links work: https://stackoverflow.com/questions/60193771/a-badge-in-github-template-repository-that-will-refer-to-clones-build-status-n--->
[![Build and Deploy](../../actions/workflows/build-deploy.yml/badge.svg)](../../actions/workflows/build-deploy.yml)


## Template contents
- TeX source file: [`main.tex`](main.tex)
- Index page template: [`index.md`](index.md) (used for GitHub Pages)
- Bibtex bibliography file: [`references.bib`](references.bib)
- Example PDF figure: [`darwin-rock.pdf`](figures/darwin-rock.pdf)
- [`latexmkrc`](latexmkrc) file for optional customization of build directives (see [`latexmk`](https://mg.readthedocs.io/latexmk.html) docs)
- GitHub Actions workflow file (building and deploying PDFs): [`.github/workflows/build-deploy.yml`](.github/workflows/build-deploy.yml)

## Automatic Document Compilation

This template automatically compiles all `.tex` files [`index.md`](index.md) to PDFs. You can simply:

1. Add your LaTeX files to the repository root
2. Update the [`index.md`](index.md) file to include links to your new files
3. Push changes to the main branch
4. All PDFs will be automatically compiled and deployed to GitHub Pages


## Dependencies

 - TeX Live: [www.tug.org/texlive/]()

## PDF compilation

> [!NOTE]
> It is not necessary to commit compiled PDF files from your local build.
> The [`.gitignore`](.gitignore) is set to ignore PDF files in the root directory.
> If you want to commit PDF files (i.e. for figures), put them in a subdirectory.

### Testing

A GitHub Action, triggered by push, automatically compiles all LaTeX files to PDF and publishes them to GitHub Pages.
The PDFs can be accessed as artifacts of each action run.
Click the badge icon at the top of this README to access these runs.
If TeX compilation errors occur, the badge will reflect this, and the author of the breaking changes will receive an email.

### GitHub Pages Deployment

This template includes automatic deployment to GitHub Pages. When you push to the main branch, all TeX files in the root directory will be compiled and their PDFs will be deployed to GitHub Pages.

The [`index.md`](index.md) file serves as the landing page for your GitHub Pages site. It:
- Is automatically processed by GitHub Pages using Jekyll
- Displays your repository description
- Lists links to all compiled PDF documents
- Adapts to show all compiled PDFs from your LaTeX files

#### Customizing the Index Page

You can customize the [`index.md`](index.md) file to change the layout of your GitHub Pages site. The file uses Jekyll's Liquid templating language to dynamically display content:

- `{{ site.github.project_tagline }}` displays your repository description
- The link section automatically displays links to the PDF files

If you want to add more content or change the styling, you can modify this file while keeping the dynamic link generation.

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
