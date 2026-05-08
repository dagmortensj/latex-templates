# notes-template

LaTeX template for long-form theoretical physics and mathematics notes.
JHEP/CUP-inspired layout, calm vertical rhythm, numerical citations.

## Files

| File              | Description                                |
|-------------------|--------------------------------------------|
| `main.tex`        | Starting point — content lives here        |
| `notesstyle.sty`  | All formatting; rarely changed             |
| `references.bib`  | BibTeX references; add your own here       |
| `figures/`        | Folder for figures; loaded automatically   |

## Getting started

1. Copy the entire folder to a new project
2. Open `main.tex` and fill in title, author, abstract
3. Add references to `references.bib`
4. Compile in this order:

```
pdflatex main
bibtex   main
pdflatex main
pdflatex main
```

## Useful commands

### Citations

```latex
\cite{key}                 % [1]
\cite{k1,k2,k3}            % [1-3] (sorted and compressed)
```

### Theorem environments

```latex
\begin{theorem}
  Statement of the theorem.
\end{theorem}

\begin{definition}
  Definition text.
\end{definition}

\begin{remark}
  A remark.
\end{remark}
```

All three share a single counter scoped to the section,
e.g. Theorem 2.1, Definition 2.2, Remark 2.3.

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
- **Page size:** A4, symmetric margins (3.0 cm L/R)
- **Line spacing:** 1.07
- **Paragraphs:** indented, no line break
- **Microtypography:** protrusion, expansion, tracking enabled
- **Sections:** numbered, small-caps headings
- **Citations:** numerical in square brackets, sorted and compressed
- **Bibliography:** `unsrtnat` (in citation order)
- **Hyperlinks:** dark red, print-safe
- **Table of contents:** JHEP-style, framed by horizontal rules

## Adding theorem-like environments

```latex
\theoremstyle{plain}
\newtheorem{lemma}[theorem]{Lemma}
\newtheorem{proposition}[theorem]{Proposition}

\theoremstyle{definition}
\newtheorem{example}[theorem]{Example}
```

The `[theorem]` argument means the new environment shares
the theorem counter — keeps numbering coherent across the
document.

## BibTeX sources

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for physics
- **arXiv** → Export Citation → BibTeX
