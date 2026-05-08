# article-template

Two-column LaTeX article template for English-language, essayistic
physics and mathematics articles.

## Files

| File              | Description                                      |
|-------------------|--------------------------------------------------|
| `main.tex`        | Starting point — fill in title and content       |
| `ffvstyle.sty`    | All formatting; rarely needs changing            |
| `references.bib`  | BibTeX references; add your own here             |

## Getting started

1. Copy the entire folder to a new project
2. Open `main.tex` and fill in title, author, and text
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
\cite{key}             % [1]
\cite{key1,key2}       % [1,2]
```

### Equations
```latex
\begin{equation}
  E = mc^2.
  \label{eq:einstein}
\end{equation}
% Reference with \eqref{eq:einstein}
```

### Single-column figures
```latex
\begin{figure}[t]
  \centering
  \includegraphics[width=\linewidth]{filename}
  \caption{Figure caption.}
  \label{fig:label}
\end{figure}
```

### Figures spanning both columns
```latex
\begin{figure*}[t]
  \centering
  \includegraphics[width=0.9\linewidth]{filename}
  \caption{Wide figure caption.}
  \label{fig:wide}
\end{figure*}
```

Note: `figure*` floats only to the top or bottom of pages.

### Tables
Use `booktabs` (\toprule, \midrule, \bottomrule) — avoid
vertical lines.

```latex
\begin{table}[t]
  \centering
  \caption{Table caption.}
  \label{tab:label}
  \begin{tabular}{lcr}
    \toprule
    Column 1 & Column 2 & Column 3 \\
    \midrule
    ...
    \bottomrule
  \end{tabular}
\end{table}
```

## Typography

- **Font:** STIX2 (text and mathematics)
- **References:** numbered in citation order (`unsrtnat`)
- **Paragraphs:** indented, no line break
- **Language:** English hyphenation and punctuation via `babel`
- **Tables:** booktabs style without vertical lines
- **Figures:** caption in small with bold label

## BibTeX sources

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for physics
- **arXiv** → Export Citation → BibTeX
