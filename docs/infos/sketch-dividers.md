# Hand-drawn Dividers

Sketchy separators and compact wobble borders live in
`src/utilities/_dividers.scss`, `src/utilities/_borders.scss`, and the helpers
in `src/core/_mixins.scss`. They exist so separators read as hand-drawn PaperCSS
instead of ruler-straight `1px` lines.

## Classes and tokens

- `.paper-divider`: a standalone hand-drawn horizontal rule (wavy SVG stroke).
  Works on `<hr>` or `<div>`. `.paper-divider-tight` reduces its vertical margin.
- `--paper-sketch-line`: a custom property holding the same wavy stroke as a
  `url(...)`. Consumers reuse it as a `background-image` (e.g. a section's top or
  bottom edge) without redrawing the SVG. Set per theme on `html` / `html.dark`.
- `.border-soft` (alias `.border-7`): border style 7, a softer/compact wobble
  radius for small boxes (chips, counters, list notes). It sets only the radius,
  so it layers over `.border` or an app's own `border` declaration.

## SCSS helpers

- `paper-sketch-line-url($color)`: returns the wavy stroke as a `url(...)`; feeds
  both the custom property and the mixin.
- `paper-sketch-line($color)`: sets `background-image`/`position`/`repeat`/`size`
  for the repeating horizontal stroke. Tune `background-position`/`-size` after
  including it (e.g. `bottom center` for an under-edge divider).
- `border-style(7)`: the compact wobble radius used by `.border-soft`.

## Usage

- Prefer `.paper-divider` for an explicit separator element.
- For a separator on an existing block's edge, set
  `background: var(--paper-sketch-line) repeat-x bottom center / 3.2em 0.5em;`
  (or `top center`) plus matching padding, instead of a `border-top/bottom`.
- `.paper-profile-card-header` uses `paper-sketch-line` for its header/body split.

After changing the SCSS, rebuild generated CSS with `npm run css:build`.
