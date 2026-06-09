# Selection Highlights

PaperCSS2 owns the browser text-selection treatment through
`src/utilities/_selection.scss`.

## Public Surface

- Default selection is Paper Marker through `--paper-selection-background` and
  `--paper-selection-color`.
- Preset classes are `.paper-selection-paper-marker`,
  `.paper-selection-blue-pencil`, and `.paper-selection-rose-correction`.
- Apply preset classes to `html`, `body`, or a scoped container. The global
  `::selection` rule reads inherited custom properties, so scoped containers
  can opt into a different highlight without new selectors.
- Downstream products can skip classes and set `--paper-selection-background`
  plus `--paper-selection-color` directly.

## Maintenance

- Keep light and dark values in `src/core/_config.scss` so the same preset class
  works with `html.dark`.
- Update `docs/content/docs/utilities/selection.md` when adding or renaming a
  preset.
- Rebuild with `npm run css:build` after changing selection SCSS or variables.
