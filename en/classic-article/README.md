# classic-article

Classic LaTeX article template with flexible font choice.
Suited for school articles, reports, and longer text documents.

## Files

| File              | Description                                |
|-------------------|--------------------------------------------|
| `main.tex`        | Starting point — content, font, and macros |
| `classicstyle.sty`| All formatting; rarely changed             |
| `references.bib`  | BibTeX references; add your own here       |
| `figures/`        | Folder for figures; loaded automatically   |

## Getting started

1. Copy the entire folder to a new project
2. Open `main.tex` and fill in title, author, and content
3. Choose a font (see the FONT section at the top)
4. Add references to `references.bib`
5. Compile in this order:

```
pdflatex main
bibtex   main
pdflatex main
pdflatex main
```

## Font choice

The font is chosen at the top of `main.tex`. Pick one text font:

```latex
\usepackage{mlmodern}              % Modern Latin Modern
% \usepackage{lmodern}             % Latin Modern (classic)
% \usepackage{stix2}               % STIX2 (math and text)
```

The sans-serif font is set separately (typically used for headings
or sans math):

```latex
\usepackage{helvet}                % Helvetica
```

For sans-serif headings, uncomment the `titlesec` block in main.tex:

```latex
\usepackage{titlesec}
\titleformat*{\section}{\sffamily\Large\bfseries}
\titleformat*{\subsection}{\sffamily\large\bfseries}
```

The title is always set in Latin Modern via `\fontfamily{lmr}`,
regardless of the body font.

## Useful commands

### Citations

```latex
\cite{key}                 % [1]
\cite{k1,k2,k3}            % [1-3] (sorted and compressed)
```

### Custom macros

The main file contains a collection of personal shortcuts:

```latex
\p, \ep, \e                  % \varphi, \varepsilon, \mathrm{e}
\er, \ephi                   % unit vectors
\pdd{f}{x}                   % partial derivative
\dd{f}{x}                    % ordinary derivative
\diff{x}                     % differential
\pintlim{a}{b}{f(x)}{x}      % definite integral
```

Delete, modify, or add as needed.

### Equations

```latex
\begin{equation}
  E = mc^2.
  \label{eq:einstein}
\end{equation}
% Reference with \eqref{eq:einstein}
```

### Figures

Place the figure file in the `figures/` folder, then refer to it
by filename only:

```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.7\linewidth]{filename}
  \caption{Figure caption.}
  \label{fig:label}
\end{figure}
```

`\graphicspath{{figures/}}` is set in `classicstyle.sty`, so LaTeX
finds the figures automatically without you having to write the
folder name.

`[H]` placement locks the figure exactly where it stands (requires
the `float` package, which is loaded by `classicstyle.sty`).

### Tables

Use `booktabs` (\toprule, \midrule, \bottomrule) — avoid
vertical lines.

## Typography

- **Font:** chosen in main.tex
- **Page size:** A4, 3.5 cm symmetric margins (14 cm text width)
- **Line spacing:** 1.2
- **Paragraphs:** classical indentation
- **Tables:** booktabs without vertical lines
- **Captions:** small, bold label, italic text, hanging indent
- **Title:** always in Latin Modern, regardless of body font
- **Hyphenation:** off by default (`hyphenat[none]`)
- **References:** numerical in square brackets, sorted in citation order (`unsrtnat`)

## BibTeX sources

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for physics
- **arXiv** → Export Citation → BibTeX
