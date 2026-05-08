# handout-template

LaTeX template for physics and mathematics handouts and problem sheets.
Calm typography, exercise environment, dark red separator rules.

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

\begin{enumerate}
  \item First subproblem.
  \item Second subproblem.
\end{enumerate}
\end{exercise}
```

Exercises are numbered per section (e.g. Exercise 2.1, 2.2)
and use lowercase letter labels for subproblems (a, b, c).

Use `\begin{enumerate}[resume]` to continue the same letter
sequence after explanatory prose between subproblems.

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

## Localizing the exercise label

`handoutstyle.sty` defines `\exercisename` as `Exercise` by
default. To change it (e.g. for a Norwegian handout), override
before loading the style:

```latex
\providecommand{\exercisename}{Oppgave}
\usepackage{handoutstyle}
```
