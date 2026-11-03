# PLATONIA design notes

One page listing every address that belongs to one person. Plain HTML, no
build step, no dependency. The register is the aerial page; the surface is
black paper with white ink.

## Palette

```
paper   #0b0b0b
ink     #f2f0ea
```

Two colours. Nothing else, no accent hue: the links are the same ink as the
text, and hierarchy comes from size, spacing and letter-spacing alone.

## Type

`ui-monospace` with the system fallbacks, 15px / 1.62. Labels 12px, 500,
letter-spacing 0.2em, uppercase. One family, two weights.

## Layout

One column, 76ch, centred. 104px above the plate, 176px below the last row,
104px between sections, 22px between rows. A row is a two-column grid: the
name on the left, its lamps on the right.

## The lamps

Every address a work is reachable at gets one 7px circle, ordered by
preference. Each circle is itself a link to that address, so a reader can pick
a host by hand; the row's name goes to the first address that answers.

A lamp is checked on load and filled on a 900ms curve, staggered 260ms plus
jitter, so a row lights in sequence instead of appearing complete. Every five
seconds one lamp is re-tested at random: it dips and comes back, which is the
only motion on the page. A single failed re-test never puts a working lamp out, because the
network stutters more often than a host dies.

Two probes are used because one is not enough: a no-cors `fetch`, and if that
is refused (bot walls), a load of the site's icon, which browsers fetch under
different rules.

## What is deliberately absent

No image, no icon of any platform, no logo, no "verified" badge, no analytics,
no web font. The page reads as plain text with CSS off and still makes sense
printed.

## Identity

`rel="me"` to the other site copies and to Mastodon, plus a JSON-LD `sameAs`
naming every account. Those are the only machine-readable parts; everything
visible is the list itself.
