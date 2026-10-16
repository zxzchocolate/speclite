# Speclite

**A small, human-readable image format experiment.**

Speclite stores pixels as UTF-8 text: each character identifies a palette color, and each palette entry maps a character to a hexadecimal RGB value.

## Try it

Open the [Speclite converter](https://zxzchocolate.github.io/speclite/) (after GitHub Pages is enabled). It runs in your browser and can convert images to `.speclite`, render Speclite files, and export the preview as PNG. No uploads to a server.

## Format v1

```text
SPECLITE/1
WIDTH 3
HEIGHT 3
PIXELS
ABC
CBA
ABC
COLORS
A:FFFFFF
B:000000
C:FF0000
END
```

- `SPECLITE/1`: format signature and version.
- `WIDTH` and `HEIGHT`: pixel dimensions.
- `PIXELS`: exactly one row per line, with one symbol per pixel.
- `COLORS`: `symbol:RRGGBB` palette entries.
- `END`: terminates the document.

Version 1 uses opaque RGB colors. The browser converter quantizes the image to a limited palette; its current palette selection is deliberately simple and experimental.

## Is it lightweight?

Not necessarily yet. Text is easy to inspect and edit, but a character per pixel can be much larger than compressed binary formats. Speclite is an experiment in a readable representation, not a claim to beat JPEG, WebP, or AVIF. Future versions could explore run-length encoding, alpha support, better palette selection, and a compact binary variant.

## Project status

Early prototype. The file format may change before a stable specification is published.

## License

Not specified yet.
