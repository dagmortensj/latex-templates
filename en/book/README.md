# book-template

LaTeX book template in CUP style with superscript citations.

## Files

| File                   | Description                                    |
|------------------------|------------------------------------------------|
| `main.tex`             | Starting point — structure and content         |
| `bookstyle.sty`        | All formatting; frozen, rarely changed         |
| `references.bib`       | BibTeX references; add your own here           |
| `content/chapter1.tex` | Example chapter; copy and create more          |
| `figures/`             | Folder for figures; loaded automatically       |

## Getting started

1. Copy the entire folder to a new project
2. Open `main.tex` and fill in title, author, dedication
3. Write chapters in the `content/` folder and include with `\input{content/...}`
4. Add references to `references.bib`
5. Compile in this order:

```
pdflatex main
bibtex   main
pdflatex main
pdflatex main
```

## Structure

The book is divided into three phases:

| Phase         | Command         | Contents                                         |
|---------------|-----------------|--------------------------------------------------|
| Front matter  | `\frontmatter`  | Title, dedication, TOC, preface, acknowledgments |
| Main matter   | `\mainmatter`   | Introduction, parts and chapters                 |
| Back matter   | `\backmatter`   | Bibliography, index                              |

## Useful commands

### Page templates

```latex
\booktitlepage             % Title page
\dedicationpage{...}       % Dedication (recto, centered italic)
\booktoc                   % Table of contents
\frontchapter{Preface}     % Unnumbered chapter in front matter
```

### Chapter opening with drop cap

```latex
\chapter{Chapter Title}
\chapteropening{T}{he first sentence}
continues here. The opening paragraph must be long enough
to fill the vertical space reserved by the drop cap, otherwise
the next section heading will collide with the drop cap.
```

### Citations

```latex
\cite{key}                 % superscript: ¹
\cite{k1,k2,k3}            % sorted and compressed: ¹⁻³
```

Placement: directly after the word, not after punctuation.

### Equations

```latex
\begin{equation}
  E = mc^2.
  \label{eq:einstein}
\end{equation}
% Reference with \eqref{eq:einstein}
```

### Figures

```latex
\begin{figure}[t]
  \centering
  \includegraphics[width=0.8\linewidth]{filename}
  \caption{Figure caption.}
  \label{fig:label}
\end{figure}
```

### Tables

Use `booktabs` (\toprule, \midrule, \bottomrule) — avoid
vertical lines.

## Typography

- **Font:** Latin Modern (T1)
- **Page size:** A4 (draft) or B5 (print), via `\documentclass`
- **Margins:** asymmetric for binding (inner 2.7 cm, outer 2.3 cm)
- **Line spacing:** 1.07
- **Paragraphs:** indented, no line break
- **Microtypography:** protrusion, expansion, tracking enabled
- **Sections:** unnumbered, but appear in TOC
- **Citations:** superscript numbers, placed exactly where written
- **Bibliography:** `1.` instead of `[1]`, sorted by citation order

## Changing paper size

```latex
\documentclass[11pt,twoside,a4paper]{book}   % draft
\documentclass[11pt,twoside,b5paper]{book}   % print
```

Margins adapt automatically.

## BibTeX sources

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for physics
- **arXiv** → Export Citation → BibTeX
