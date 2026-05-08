# handout-mal

LaTeX-mal for fysikk- og matematikknotater og oppgavesett.
Rolig typografi, oppgaveomgivelse, mørkerøde separatorlinjer.

## Filer

| Fil               | Beskrivelse                                |
|-------------------|--------------------------------------------|
| `main.tex`        | Utgangspunktet — innholdet skrives her     |
| `handoutstyle.sty`| All formatering; endres sjelden            |
| `figurer/`        | Mappe for figurer; lastes automatisk       |

## Kom i gang

1. Kopier hele mappen til et nytt prosjekt
2. Åpne `main.tex` og fyll inn tittel, dato, innhold
3. Kompiler:

```
pdflatex main
pdflatex main
```

(Ingen bibliografi som standard — handouts og oppgavesett
trenger sjelden det. Legg til `natbib` og en `.bib`-fil
hvis du noen gang skulle trenge det.)

## Nyttige kommandoer

### Oppgaver

```latex
\begin{exercise}
Oppgavetekst.

\begin{enumerate}
  \item Første deloppgave.
  \item Andre deloppgave.
\end{enumerate}
\end{exercise}
```

Oppgaver nummereres per seksjon (f.eks. Oppgave 2.1, 2.2)
og bruker små bokstavetiketter for deloppgaver (a, b, c).

Bruk `\begin{enumerate}[resume]` for å fortsette samme
bokstavsekvens etter forklarende tekst mellom deloppgaver.

### Separator

```latex
\separator
```

En tynn mørkerød linje med vertikalt mellomrom på begge
sider. Bruk mellom innholdsblokker — etter en oppgave,
mellom eksempler, eller ved temaskifter innen en seksjon.

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

## Typografi

- **Font:** Latin Modern (T1)
- **Sideoppsett:** A4, symmetriske marger (3.0 cm V/H)
- **Linjeavstand:** 1.04
- **Avsnitt:** innrykk, ikke linjeskift
- **Mikrotypografi:** protrusion, expansion, tracking aktivert
- **Seksjoner:** stille, normal størrelse i fet (ingen overdimensjonerte fonter eller streker)
- **Tittelblokk:** kapiteler, sperret, sentrert
- **Hyperlenker og linjer:** mørkerøde, trygt for trykk

## Lokalisere oppgaveetiketten

`handoutstyle.sty` definerer `\exercisename` som `Oppgave` som
standard. For å endre den (f.eks. for et engelsk handout),
overstyr før stilen lastes:

```latex
\providecommand{\exercisename}{Exercise}
\usepackage{handoutstyle}
```
