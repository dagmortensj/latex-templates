# latex-templates

A small collection of personal LaTeX templates for academic and
teaching work — books, articles, lecture notes, problem sheets.
Each template is self-contained and available in both English and
Norwegian.

## Templates

Each template has an English version in `en/` and a Norwegian
version in `no/`:

| Template            | Description                                                                  |
|---------------------|------------------------------------------------------------------------------|
| **book**            | CUP-style monograph: parts, chapters, drop caps, superscript citations       |
| **classic-article** | Classic article with flexible font choice and rich utility packages          |
| **ffv**             | Two-column physics/math article (JHEP-inspired) with STIX2 typography        |
| **handout**         | Problem sheets with built-in exercise environment and separator rules        |
| **notes**           | Long-form theoretical notes with theorem environments and JHEP-style TOC     |

## Quick start

1. Copy the template folder you want into a new project
2. Open the new copy's `README.md` for template-specific guidance
3. Edit `main.tex` — the document body is sectioned for easy navigation
4. Compile with `pdflatex` (each template's README documents the exact compile order)

Each template ships with:

- `main.tex` — the document body, with example content demonstrating the template's features
- A style file (`bookstyle.sty`, `notesstyle.sty`, `klassiskstil.sty`, ...) — all formatting lives here
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

## License

[MIT](LICENSE) — use, modify, and redistribute freely. Attribution is
appreciated but not required.

## Notes

These templates reflect my own conventions and aesthetic preferences
for academic and teaching documents. They're shared in case they're
useful to others — feel free to fork and adapt to your own needs.
