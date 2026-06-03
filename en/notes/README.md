# notes-template

LaTeX template for long-form theoretical physics and mathematics notes.
CUP-inspired book typography in article form, with theorem and exercise
environments, a JHEP-style framed table of contents, and numbered citations.

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

### Table of contents

```latex
\framedtoc
```

Renders the contents framed by a rule above and below (JHEP-style),
with no dot leaders. In the template it sits on its own page,
between the front page and the body. Plain `\tableofcontents` still
works if you ever want an unframed list.

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

### Exercises

```latex
\begin{exercise}
Prompt for the exercise.

\begin{subproblems}
  \item First subproblem.
  \item Second subproblem.
\end{subproblems}
\end{exercise}
```

Exercises are numbered per section (e.g. Exercise 4.1, 4.2),
independently of the theorem counter, and use lowercase
letter labels for subproblems (a, b, c). The `subproblems`
environment leaves ordinary `enumerate` lists untouched.

Use `\begin{subproblems}[resume]` to continue the same letter
sequence after explanatory prose between subproblems.

### Separator

```latex
\separator
```

A thin dark red rule with vertical space on either side.
Use between content blocks — after an exercise, between
examples, or at a topic shift within a section. It can be
called anywhere in the normal document flow.

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
- **Sections:** numbered, bold headings
- **Subsubsections:** quiet run-in heading, kept out of the table of contents
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

## Localizing labels

`notesstyle.sty` sets the structured-environment labels in
English by default. Override any of them *before* loading the
style (e.g. for Norwegian notes):

```latex
\providecommand{\theoremname}{Teorem}
\providecommand{\definitionname}{Definisjon}
\providecommand{\remarkname}{Merknad}
\providecommand{\exercisename}{Oppgave}
\usepackage{notesstyle}
```

## BibTeX sources

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for physics
- **arXiv** → Export Citation → BibTeX
