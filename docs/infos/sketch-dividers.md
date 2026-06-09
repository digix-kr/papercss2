# Hand-drawn Dividers

Sketchy separators and compact wobble borders live in
`src/utilities/_dividers.scss`, `src/utilities/_borders.scss`, and the helpers
in `src/core/_mixins.scss`. They exist so separators read as hand-drawn PaperCSS
instead of ruler-straight `1px` lines.

## Classes and tokens

- `.paper-divider`: a standalone hand-drawn horizontal rule (wavy SVG stroke).
  Works on `<hr>` or `<div>`. `.paper-divider-tight` reduces its vertical margin.
- `.paper-divider-faint`: a low-contrast separator for dense lists, comments, and
  compact stacks.
- `--paper-sketch-line`: a custom property holding the same wavy stroke as a
  `url(...)`. Consumers reuse it as a `background-image` (e.g. a section's top or
  bottom edge) without redrawing the SVG. Set per theme on `html` / `html.dark`.
- `--paper-sketch-line-faint`: the same reusable token with lower stroke opacity.
- `--paper-sketch-line-vertical`: the wavy stroke rotated to run top-to-bottom,
  for left-edge quote bars. Set per theme on `html` / `html.dark`.
- `.paper-quote`: a hand-drawn quote bar (wavy vertical stroke pinned to the left
  edge plus left padding), the PaperCSS replacement for a `border-left` on
  quoted/shared content. Uses `--paper-sketch-line-vertical`, so it follows
  light/dark automatically; layer product spacing in app CSS around it.
- `.border-soft` (alias `.border-7`): border style 7, a softer/compact wobble
  radius for small boxes (chips, counters, list notes). It sets only the radius,
  so it layers over `.border` or an app's own `border` declaration.

## SCSS helpers

- `paper-sketch-line-url($color)`: returns the wavy stroke as a `url(...)`; feeds
  both the custom property and the mixin.
- `paper-sketch-line-faint-url($color)`: returns the low-contrast divider stroke.
- `paper-sketch-line($color)`: sets `background-image`/`position`/`repeat`/`size`
  for the repeating horizontal stroke. Tune `background-position`/`-size` after
  including it (e.g. `bottom center` for an under-edge divider).
- `paper-sketch-line-faint($color)`: applies the faint repeating divider stroke.
- `paper-sketch-line-vertical-url($color)`: returns the wavy vertical stroke as a
  `url(...)`; feeds `--paper-sketch-line-vertical` and the vertical mixin.
- `paper-sketch-line-vertical($color)`: sets the repeating vertical stroke pinned
  to the left edge (used by `.paper-quote`).
- `border-style(7)`: the compact wobble radius used by `.border-soft`.

## Usage

- Prefer `.paper-divider` for an explicit separator element.
- For a separator on an existing block's edge, set
  `background: var(--paper-sketch-line) repeat-x bottom center / 3.2em 0.5em;`
  (or `top center`) plus matching padding, instead of a `border-top/bottom`.
- For compact item separators, use `--paper-sketch-line-faint` with tighter
  spacing instead of a straight `1px` border.
- `.paper-profile-card-header` uses `paper-sketch-line` for its header/body split.

After changing the SCSS, rebuild generated CSS with `npm run css:build`.
