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

## The one inverted element

The plate carries the name as a solid ink chip with paper-coloured type: the
only filled shape on the page. It is what the eye lands on first, and it costs
one line of CSS. Nothing else is boxed, so the chip reads as a signature rather
than a button.

## Mirrors in the right column

Rows whose work exists on three hosts list the alternates (`gitlab · codeberg`)
in the muted column, while the name links to the GitHub copy. The homepage and
the blog are the exception: they link to their `pages.dev` address, because that
is where those two are served from. When GitHub is unreachable the reader still
has a working second and third address one click away, without the page needing
JavaScript to probe anything.

## Identity, not decoration

The page carries `rel="me"` to the other site copies and to Mastodon, and a
JSON-LD `sameAs` list that names every account. Those are the only machine
readable parts; everything visible is the plain listing.
