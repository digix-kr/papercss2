# Selection Highlights

PaperCSS2 owns the browser text-selection treatment through
`src/utilities/_selection.scss`.

## Public Surface

- Default selection is Paper Marker through `--paper-selection-background` and
  `--paper-selection-color`.
- Preset classes are `.paper-selection-paper-marker`,
  `.paper-selection-blue-pencil`, and `.paper-selection-rose-correction`.
- `.paper-selection-brushed` makes the native rectangular selection fill
  transparent and expects an app/runtime to render `.paper-selection-brush-layer` with
  `.paper-selection-brush-mark` children over the selected text rects.
- Brushed overlays expose size controls:
  `--paper-selection-brush-height-scale`, `--paper-selection-brush-min-height`,
  and `--paper-selection-brush-horizontal-bleed`.
- Apply preset classes to `html`, `body`, or a scoped container. The global
  `::selection` rule reads inherited custom properties, so scoped containers
  can opt into a different highlight without new selectors.
- Downstream products can skip classes and set `--paper-selection-background`
  plus `--paper-selection-color` directly.
- Browser-native `::selection` cannot draw non-rectangular marker edges; use
  the brush overlay classes when the product needs a hand-painted selection.
- iOS Safari does not support `::selection`; do not enable brushed overlays
  there unless the product accepts native blue selection or a bespoke fallback.

## Maintenance

- Keep light and dark values in `src/core/_config.scss` so the same preset class
  works with `html.dark`.
- Update `docs/content/docs/utilities/selection.md` when adding or renaming a
  preset.
- Keep overlay class names stable because downstream apps can implement their
  own selection-rect renderer against those classes.
- Rebuild with `npm run css:build` after changing selection SCSS or variables.
