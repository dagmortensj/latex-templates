# artikkel-template

Tokolonne LaTeX-artikkelmal for norskspråklige, essayistiske
fysikk- og matematikkartikler.

## Filer

| Fil               | Beskrivelse                                      |
|-------------------|--------------------------------------------------|
| `main.tex`        | Utgangspunktet — fyll inn tittel og innhold      |
| `ffvstil.sty`     | All formatering; trenger sjelden endres          |
| `referanser.bib`  | BibTeX-referanser; legg til dine egne her        |

## Kom i gang

1. Kopier hele mappen til et nytt prosjekt
2. Åpne `main.tex` og fyll inn tittel, forfatter og tekst
3. Legg referanser inn i `referanser.bib`
4. Kompiler i denne rekkefølgen:

```
pdflatex main
bibtex   main
pdflatex main
pdflatex main
```

## Nyttige kommandoer

### Siteringer
```latex
\cite{nokkel}            % [1]
\cite{nokkel1,nokkel2}   % [1,2]
```

### Ligninger
```latex
\begin{equation}
  E = mc^2.
  \label{eq:einstein}
\end{equation}
% Referer med \eqref{eq:einstein}
```

### Figurer i én kolonne
```latex
\begin{figure}[t]
  \centering
  \includegraphics[width=\linewidth]{filnavn}
  \caption{Figurtekst.}
  \label{fig:etikett}
\end{figure}
```

### Figurer over begge kolonner
```latex
\begin{figure*}[t]
  \centering
  \includegraphics[width=0.9\linewidth]{filnavn}
  \caption{Bred figurtekst.}
  \label{fig:bred}
\end{figure*}
```

Merk: `figure*` flyter bare til topp eller bunn av sider.

### Tabeller
Bruk `booktabs` (\toprule, \midrule, \bottomrule) — unngå
vertikale streker.

```latex
\begin{table}[t]
  \centering
  \caption{Tabelltekst.}
  \label{tab:etikett}
  \begin{tabular}{lcr}
    \toprule
    Kolonne 1 & Kolonne 2 & Kolonne 3 \\
    \midrule
    ...
    \bottomrule
  \end{tabular}
\end{table}
```

## Typografi

- **Font:** STIX2 (tekst og matematikk)
- **Referanser:** nummererte i siteringsrekkefølge (`unsrtnat`)
- **Avsnitt:** innrykk, ikke linjeskift
- **Språk:** norsk orddeling og tegnsetting via `babel`
- **Tabeller:** booktabs-stil uten vertikale streker
- **Figurer:** figurtekst i small med fet etikett

## BibTeX-kilder

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for fysikk
- **arXiv** → Export Citation → BibTeX
