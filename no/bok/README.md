# bok-mal

LaTeX-bokmal i CUP-stil med superskriftsiteringer.

## Filer

| Fil                    | Beskrivelse                                  |
|------------------------|----------------------------------------------|
| `main.tex`             | Utgangspunktet — struktur og innhold         |
| `bokstil.sty`          | All formatering; frosset, endres sjelden     |
| `referanser.bib`       | BibTeX-referanser; legg til dine egne her    |
| `innhold/kapittel1.tex`| Eksempelkapittel; kopiér og lag flere        |
| `figurer/`             | Mappe for figurer; lastes automatisk         |

## Kom i gang

1. Kopier hele mappen til et nytt prosjekt
2. Åpne `main.tex` og fyll inn tittel, forfatter, dedikasjon
3. Skriv kapitler i `innhold/`-mappen og inkluder med `\input{innhold/...}`
4. Legg referanser inn i `referanser.bib`
5. Kompiler i denne rekkefølgen:

```
pdflatex main
bibtex   main
pdflatex main
pdflatex main
```

## Struktur

Boken er delt i tre faser:

| Fase           | Kommando        | Innhold                                       |
|----------------|-----------------|-----------------------------------------------|
| Frontmateriale | `\frontmatter`  | Tittel, dedikasjon, innhold, forord, takk     |
| Hovedmateriale | `\mainmatter`   | Innledning, deler og kapitler                 |
| Bakmateriale   | `\backmatter`   | Bibliografi, indeks                           |

## Nyttige kommandoer

### Sidemaler

```latex
\booktitlepage             % Tittelside
\dedicationpage{...}       % Dedikasjon (recto, sentrert kursiv)
\booktoc                   % Innholdsfortegnelse
\frontchapter{Forord}      % Unummerert kapittel i frontmateriale
```

### Kapittelåpning med initial

```latex
\chapter{Kapitteltittel}
\chapteropening{D}{en første setningen}
fortsetter her. Åpningsavsnittet må være langt nok
til å fylle ut høyden av initialen, ellers vil neste
seksjonsoverskrift krasje med initialen.
```

### Siteringer

```latex
\cite{nokkel}              % superskript: ¹
\cite{n1,n2,n3}            % sortert og komprimert: ¹⁻³
```

Plassering: rett etter ordet, ikke etter tegnsetting.

### Ligninger

```latex
\begin{equation}
  E = mc^2.
  \label{eq:einstein}
\end{equation}
% Referer med \eqref{eq:einstein}
```

### Figurer

```latex
\begin{figure}[t]
  \centering
  \includegraphics[width=0.8\linewidth]{filnavn}
  \caption{Figurtekst.}
  \label{fig:etikett}
\end{figure}
```

### Tabeller

Bruk `booktabs` (\toprule, \midrule, \bottomrule) — unngå
vertikale streker.

## Typografi

- **Font:** Latin Modern (T1)
- **Sideoppsett:** A4 (utkast) eller B5 (trykk), via `\documentclass`
- **Marger:** asymmetriske for innbinding (innside 2.7 cm, utside 2.3 cm)
- **Linjeavstand:** 1.07
- **Avsnitt:** innrykk, ikke linjeskift
- **Mikrotypografi:** protrusion, expansion, tracking aktivert
- **Seksjoner:** unummererte, men i innholdsfortegnelse
- **Siteringer:** superskript-tall, plassert nøyaktig der de står
- **Bibliografi:** `1.` istedenfor `[1]`, sortert i siteringsrekkefølge

## Endre papirstørrelse

```latex
\documentclass[11pt,twoside,a4paper]{book}   % utkast
\documentclass[11pt,twoside,b5paper]{book}   % trykk
```

Margene tilpasser seg automatisk.

## BibTeX-kilder

- **Google Scholar** → Cite → BibTeX
- **Inspire-HEP** (inspirehep.net) — for fysikk
- **arXiv** → Export Citation → BibTeX
