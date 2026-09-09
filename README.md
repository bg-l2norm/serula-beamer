# Serula

A very lovely, rather elegant, and exceptionally legible serif Beamer theme for (mainly) mathematical talks, classes, and slide shows.

Crimson Pro Regular for body text; STIX Two Math for the equations.

## Make it yours

Open `main.tex`.

1. Change the title, subtitle, name, and affiliation at the top. The optional
   argument in `\title[Short title]{Full title}` sets the banner text on content
   slides. Leave `\date{}` empty to omit the date.
2. Edit the slides in order. The examples cover lists, equations, tables,
   figures, animation, and references.
3. Duplicate a content frame to add a slide. Numbering updates automatically;
   the intro stays unnumbered, with no title in its banner.

Keep `beamerthemeSerula.sty` beside `main.tex`. You only need to edit it
if you want to change the appearance.

The example drawing and animation share `figures/moving-dot.tex`. If you remove the
visuals demo, remove its `\input` line from `main.tex` too.

The final slide uses `thebibliography` with placeholder book and article entries.
Replace them with your sources; use `\cite{sample-book}` or your own entry key
to cite an entry in a slide. No separate `.bib` file or BibTeX run is required.

## Compile

Choose **XeLaTeX**, not pdfLaTeX, in your editor. From a terminal:

```sh
latexmk -xelatex main.tex
```

The theme loads Beamer's Madrid theme, `fontspec`, `unicode-math`, `mathtools`,
`microtype`, `booktabs`, `graphicx`, TikZ, and `animate`. These packages must be
available in your TeX installation.

The fonts are not bundled. XeLaTeX must be able to find these files:

- `CrimsonPro-Regular.ttf`
- `CrimsonPro-Italic.ttf`
- `CrimsonPro-Bold.ttf`
- `CrimsonPro-BoldItalic.ttf`
- `STIXTwoMath-Regular.otf`

If a font is reported missing, check that the corresponding file is visible to
your TeX installation. The font declarations are near the top of
`beamerthemeSerula.sty`.

To remove intermediate build files while keeping the PDF:

```sh
latexmk -c main.tex
```

## Present

Test animations in the PDF viewer you will use for your talk. Some viewers
and editor previews show only the first frame.

## Template files

Keep these files together when sharing the template:

- `main.tex` — the example presentation.
- `beamerthemeSerula.sty` — the theme and helper commands.
- `figures/moving-dot.tex` — the drawing used in the figures demo.
- `README.md` — setup and usage instructions.

You can include `main.pdf` as a preview. Intermediate build files are not needed.
