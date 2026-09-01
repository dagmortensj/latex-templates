# pdflatex-templates

A small collection of personal LaTeX templates for academic and
teaching work — books, articles, lecture notes, problem sheets.
Each template is self-contained and available in both English and
Norwegian.

## Templates

Each template has an English version in `en/` and a Norwegian
version in `no/`:

| Template    | Description              | Features                                                                    |
|-------------|--------------------------|-----------------------------------------------------------------------------|
| **book**    | CUP-style monograph      | parts, chapters, drop caps, superscript citations                           |
| **ffv**     | JHEP two-column article  | STIX2 typography, numbered citations                                        |
| **handout** | Problem sheets           | theorem environments, exercises, emphasis boxes, python code; optional unnumbered mode |
| **notes**   | CUP-style lecture notes  | theorem environments, exercises, emphasis boxes, python code; framed TOC, numbered citations|

All templates include figure and table support.

## Quick start

1. Copy the template folder you want into a new project
2. Open the new copy's `README.md` for template-specific guidance
3. Edit `main.tex` — the document body is sectioned for easy navigation
4. Compile with `pdflatex` (each template's README documents the exact compile order)

Each template ships with:

- `main.tex` — the document body, with example content demonstrating the template's features
- A style file (`bookstyle.sty`, `notesstyle.sty`, `handoutstyle.sty`, ...) — all formatting lives here
- A `.bib` file with example bibliography entries
- A `figures/` (or `figurer/`) folder with a stock figure
- A `README.md` documenting the template's features and conventions

The bundled `main.pdf` lets you preview what each template produces without compiling.

## Languages

The English (`en/`) and Norwegian (`no/`) versions are functionally
equivalent. The differences are:

- **Babel** — `[english]` vs `[norsk]`
- **Filenames** — Norwegian versions use Norwegian names
  (`bok` instead of `book`, `referanser.bib` instead of `references.bib`,
  `bokstil.sty` instead of `bookstyle.sty`, etc.)
- **Comments and placeholder text** — written in the matching language

The layout, packages, and typography are identical between the two versions.

## Parity between the editions

The two editions are meant to differ only in language strings,
filenames and comments. `tools/parity-diff.sh` strips comments,
maps the Norwegian identifiers to their English counterparts, and
diffs each pair of style files and `main.tex` — run it from the
repository root after editing either edition. The script's header
lists the few legitimate residual differences.

## License

[MIT](LICENSE) — use, modify, and redistribute freely. Attribution is
appreciated but not required.

## Notes

These templates reflect my own conventions and aesthetic preferences
for academic and teaching documents. They're shared in case they're
useful to others — feel free to fork and adapt to your own needs.

## Acknowledgements

These templates were developed in collaboration with Claude (Anthropic).
Comments in style files and README documentation were written by Claude
and reviewed for accuracy, but may contain errors or imprecisions.
