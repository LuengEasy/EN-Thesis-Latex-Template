# English Thesis Template

### Overview

This repository provides a LaTeX template for an English master's thesis based on `bxjsreport`.
It is configured for `xelatex` and includes a title page, abstract, table of contents, main chapters, acknowledgements, references, and a research achievements page.

### File Structure

- `main.tex`: Main entry file of the thesis.
- `body.tex`: Main chapter and section contents.
- `English_thesis.sty`: Local style file for title page and thesis formatting.
- `references.bib`: BibTeX database.
- `rm2c_junsrt.bst`: Bibliography style file.
- `latexmkrc`: Build configuration for `latexmk`.
- `figures/`: Directory for figures and images.
- `fonts/`: Optional local fonts. Put `CENTURY.TTF` here if you need the exact Century font.
- `build/`: Output directory for auxiliary files and the generated PDF.

### Requirements

Please make sure the following tools are available in your TeX environment:

- `xelatex`
- `upbibtex`
- `latexmk`

This template was prepared for a TeX Live environment.

### Fonts

The template tries to use Century in the following order:

1. `fonts/CENTURY.TTF`
2. `C:/Windows/Fonts/CENTURY.TTF`
3. `TeX Gyre Schola`

The repository does not include `CENTURY.TTF`. If you need exact Century output, add the font file yourself at:

```text
fonts/CENTURY.TTF
```

Reference entries use Times New Roman when it is available. If the font is not available, the template falls back to `TeX Gyre Termes` so Overleaf can still compile.

### How to Compile

Compile the thesis from the project root:

```bash
latexmk -pdf main.tex
```

The generated PDF will be placed here:

```text
build/main.pdf
```

To clean auxiliary files:

```bash
latexmk -c
```

To clean almost everything including the generated PDF:

```bash
latexmk -C
```

### Overleaf

Set the Overleaf compiler to **XeLaTeX**. The template compiles without uploading Century because it falls back to `TeX Gyre Schola`.

For exact Century output on Overleaf, upload the font file as:

```text
fonts/CENTURY.TTF
```

The file name is case-sensitive on Overleaf, so `CENTURY.TTF` must match exactly.

### How to Edit the Thesis

#### 1. Update Thesis Information

Edit the metadata in `main.tex`:

- `\thesisyear{...}`
- `\thesisdegree{...}`
- `\thesistitle{...}`
- `\thesissupervisor{...}`
- `\affiliationlineone{...}`
- `\affiliationlinetwo{...}`
- `\affiliationlinethree{...}`
- `\studentid{...}`
- `\studentname{...}`

#### 2. Write the Abstract

Edit the `abstract` environment in `main.tex`:

```tex
\begin{abstract}
...
\keywords{
...
}
\end{abstract}
```

#### 3. Write Main Chapters

Edit `body.tex` to add or revise chapters and sections.

Example:

```tex
\chapter{Introduction}
\section{Background}
```

#### 4. Manage References

Add bibliography entries to `references.bib`, then cite them in the thesis as usual.

The reference section is controlled in `main.tex` by:

```tex
\bibliographystyle{rm2c_junsrt}
\bibliography{references}
```

If you want to disable the bibliography temporarily, change:

```tex
\usebibliographytrue
```

to:

```tex
\usebibliographyfalse
```

#### 5. Acknowledgements

Edit the acknowledgements text in `main.tex` under:

```tex
\section*{Acknowledgements}
```

#### 6. Research Achievements

Edit the research achievements section in `main.tex` under:

```tex
\section*{Research Achievements}
```

The current template uses numbered list items in `1.`, `2.`, `3.` order.
The command below can be used to underline your own name:

```tex
\achievementauthor{Your Name}
```

Example:

```tex
\item \achievementauthor{Your Name}, Coauthor, and Coauthor, ``Paper Title,'' ...
```

### Figures

Place image files in the `figures/` directory and include them in LaTeX as needed.

Example:

```tex
\begin{figure}[t]
    \centering
    \includegraphics[width=0.8\linewidth]{figures/example.pdf}
    \caption{Example figure.}
    \label{fig:example}
\end{figure}
```

### Notes

- The template is currently set up for English thesis writing.
- The title page labels and some structural names are customized in `English_thesis.sty`.
- `Acknowledgements`, `References`, and `Research Achievements` are included in the table of contents manually.
