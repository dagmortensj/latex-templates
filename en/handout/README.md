# handout-template

LaTeX template for physics and mathematics handouts and problem sheets.
Calm, classic typography with theorem and exercise environments, lettered
subproblems, and dark red separator rules.

## Files

| File              | Description                                |
|-------------------|--------------------------------------------|
| `main.tex`        | Starting point — content lives here        |
| `handoutstyle.sty`| All formatting; rarely changed             |
| `figures/`        | Folder for figures; loaded automatically   |

## Getting started

1. Copy the entire folder to a new project
2. Open `main.tex` and fill in title, date, content
3. Compile:

```
pdflatex main
pdflatex main
```

(No bibliography by default — handouts and problem sheets
typically don't need one. Add `natbib` and a `.bib` file
if you ever do.)

## Useful commands

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

Exercises are numbered per section (e.g. Exercise 2.1, 2.2)
and use lowercase letter labels for subproblems (a, b, c).
The `subproblems` environment leaves ordinary `enumerate`
lists untouched for normal use.

Use `\begin{subproblems}[resume]` to continue the same letter
sequence after explanatory prose between subproblems.

### Theorem-like environments

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
e.g. Theorem 1.1, Definition 1.2, Remark 1.3.

### Separator

```latex
\separator
```

A thin dark red rule with vertical space on either side.
Use between content blocks — after an exercise, between
examples, or at a topic shift within a section.

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

## Typography

- **Font:** Latin Modern (T1)
- **Page size:** A4, symmetric margins (3.0 cm L/R)
- **Line spacing:** 1.04
- **Paragraphs:** indented, no line break
- **Microtypography:** protrusion, expansion, tracking enabled
- **Sections:** quiet, normal-size bold (no oversized fonts or rules)
- **Title block:** small caps, letterspaced, centered
- **Hyperlinks and rules:** dark red, print-safe

## Localizing labels

`handoutstyle.sty` sets the structured-environment labels in
English by default. Override any of them *before* loading the
style (e.g. for a Norwegian handout):

```latex
\providecommand{\theoremname}{Teorem}
\providecommand{\definitionname}{Definisjon}
\providecommand{\remarkname}{Merknad}
\providecommand{\exercisename}{Oppgave}
\usepackage{handoutstyle}
```
