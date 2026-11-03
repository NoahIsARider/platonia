# PLATONIA — design notes

A single index of every address that belongs to one person. The reference is
`noahisarider.tngl.io/aerial/`: paper, ink, one blue, monospace, no image, no
card, no border, no shadow.

## Palette

```
paper   #f7f5ef
ink     #1a1917
link    #2c4066
muted   rgba(26, 25, 23, 0.55)
```

Three colours. The muted tone is the ink at 55%, never a fourth hue.

## Type

One family: `ui-monospace` with the system fallbacks. Body 15px / 1.62. Labels
12px, weight 500, letter-spacing 0.2em, uppercase. The right column is 13px.
No second typeface, no display weight, no italic.

## Layout

One column, 76ch, centred. 104px above the plate, 176px below the last row.
Sections sit 104px apart, rows 22px apart. Nothing is boxed: separation is
vertical air alone.

A row is a two-column grid, `minmax(0, 1fr) auto`, 4ch gap. Name on the left,
the handle or host on the right, both on the same baseline. Long addresses wrap
instead of overflowing.

## Links

Names are `--link` and underline only on hover, 1px, 3px offset. Focus is a 1px
blue outline at 3px. Selection inverts to ink on paper.

## What is deliberately absent

No photographs, no icons, no logos of other platforms, no "verified" badge, no
JavaScript, no web font, no analytics. The page must be readable as plain text
with CSS disabled, and it must still make sense printed.

## Identity, not decoration

The page carries `rel="me"` to the other site copies and to Mastodon, and a
JSON-LD `sameAs` list that names every account. Those are the only machine
readable parts; everything visible is the plain listing.
