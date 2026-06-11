# handout-mal

LaTeX-mal for fysikk- og matematikknotater og oppgavesett.
Rolig, klassisk typografi med teorem- og oppgaveomgivelser,
delte deloppgaver med bokstaver, og mørkerøde separatorlinjer.

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
\begin{oppgave}
Oppgavetekst.

\begin{deloppgaver}
  \item Første deloppgave.
  \item Andre deloppgave.
\end{deloppgaver}
\end{oppgave}
```

Oppgaver nummereres per seksjon (f.eks. Oppgave 2.1, 2.2)
og bruker små bokstavetiketter for deloppgaver (a, b, c).
`deloppgaver`-omgivelsen lar vanlige `enumerate`-lister være
urørt til vanlig bruk.

Bruk `\begin{deloppgaver}[resume]` for å fortsette samme
bokstavsekvens etter forklarende tekst mellom deloppgaver.

### Teoremomgivelser

```latex
\begin{teorem}
  Formuleringen av teoremet.
\end{teorem}

\begin{definisjon}
  Definisjonstekst.
\end{definisjon}

\begin{merknad}
  En merknad.
\end{merknad}
```

Alle tre deler én teller knyttet til seksjonen,
f.eks. Teorem 1.1, Definisjon 1.2, Merknad 1.3.

### Python-kode

```latex
\begin{python}
import numpy as np

def f(x):
    return np.sin(x)   # eksempelfunksjon

print(f(np.pi / 2))
\end{python}
```

Setter Python-kode med Gruvbox Light syntaksutheving: fargede
nøkkelord, strenger, kommentarer og linjenummer på en varm kremfarget
bakgrunn, rammet opp og ned. UTF-8 er aktivert, så norske tegn
(æ, ø, å) fungerer i den omgivende teksten og i kodekommentarer.

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
- **Overskrifter:** to stille nivåer — seksjon (`\large`) og underseksjon (kroppsstørrelse), fet; ingen overdimensjonerte fonter eller streker. Underseksjonen gjør at handout-en også kan brukes som forelesningsnotater.
- **Tittelblokk:** kapiteler, sperret, sentrert
- **Hyperlenker og linjer:** mørkerøde, trygt for trykk
