# klassisk-artikkel

Klassisk LaTeX-artikkelmal med fleksibelt fontvalg.
Egnet for skoleartikler, rapporter og lengre tekstdokumenter.

## Filer

| Fil               | Beskrivelse                                |
|-------------------|--------------------------------------------|
| `main.tex`        | Utgangspunktet — innhold, font og makroer  |
| `klassiskstil.sty`| All formatering; endres sjelden            |
| `referanser.bib`  | BibTeX-referanser; legg til dine egne her  |
| `figurer/`        | Mappe for figurer; lastes automatisk       |

## Kom i gang

1. Kopier hele mappen til et nytt prosjekt
2. Åpne `main.tex` og fyll inn tittel, forfatter og innhold
3. Velg ønsket font (se FONT-seksjonen øverst)
4. Legg referanser inn i `referanser.bib`
5. Kompiler i denne rekkefølgen:

```
pdflatex main
bibtex   main
pdflatex main
pdflatex main
```

## Fontvalg

Fonten velges øverst i `main.tex`. Velg én tekstfont:

```latex
\usepackage{mlmodern}              % Modern Latin Modern
% \usepackage{lmodern}             % Latin Modern (klassisk)
% \usepackage{stix2}               % STIX2 (matte og tekst)
```

Sansserif-fonten settes separat (typisk for overskrifter eller
matematikk i sans):

```latex
\usepackage{helvet}                % Helvetica
```

For sansserif-overskrifter, fjern kommentartegnene fra
`titlesec`-blokken i `main.tex`:

```latex
\usepackage{titlesec}
\titleformat*{\section}{\sffamily\Large\bfseries}
\titleformat*{\subsection}{\sffamily\large\bfseries}
```

Tittelen settes alltid i Latin Modern via `\fontfamily{lmr}`,
uavhengig av brødtekstfonten.

## Nyttige kommandoer

### Siteringer

```latex
\cite{nokkel}              % [1]
\cite{n1,n2,n3}            % [1-3] (sortert og komprimert)
```

### Egendefinerte makroer

Hovedfilen inneholder en samling personlige snarveier:

```latex
\p, \ep, \e                  % \varphi, \varepsilon, \mathrm{e}
\er, \ephi                   % enhetsvektorer
\pdd{f}{x}                   % partiell-derivert
\dd{f}{x}                    % vanlig derivert
\diff{x}                     % differensial
\pintlim{a}{b}{f(x)}{x}      % bestemt integral
```

Slett, endre eller legg til etter behov.

### Ligninger

```latex
\begin{equation}
  E = mc^2.
  \label{eq:einstein}
\end{equation}
% Referer med \eqref{eq:einstein}
```

### Figurer

Legg figurfilen i `figurer/`-mappen, og referer kun til filnavnet:

```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.7\linewidth]{filnavn}
  \caption{Figurtekst.}
  \label{fig:etikett}
\end{figure}
```

`\graphicspath{{figurer/}}` settes i `klassiskstil.sty`, så LaTeX
finner figurene automatisk uten at du må skrive mappenavnet.

`[H]`-plassering låser figuren akkurat der den står (krever
`float`-pakken, som lastes av `klassiskstil.sty`).

### Tabeller

Bruk `booktabs` (\toprule, \midrule, \bottomrule) — unngå
vertikale streker.

## Typografi

- **Font:** velges i main.tex
- **Sideoppsett:** A4, 3,5 cm symmetriske marger (14 cm tekstbredde)
- **Linjeavstand:** 1.2
- **Avsnitt:** klassisk innrykk
- **Tabeller:** booktabs uten vertikale streker
- **Figurtekster:** små, fet etikett, kursiv tekst, hengende innrykk
- **Tittel:** alltid i Latin Modern, uavhengig av brødtekstfonten
- **Orddeling:** av som standard (`hyphenat[none]`)
- **Referanser:** numeriske i hakeparenteser, sortert i siteringsrekkefølge (`unsrtnat`)

## BibTeX-kilder

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for fysikk
- **arXiv** → Export Citation → BibTeX
