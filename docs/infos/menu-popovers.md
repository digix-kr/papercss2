# Menu Popovers

Compact app and navbar menus live in `src/components/_dropdowns.scss` beside the
JavaScript-controlled dropdown classes.

## Classes and tokens

- `--paper-menu-popover-width`: shared width for compact hamburger/dropdown
  panels. Default is `min(18rem, calc(100vw - 2rem))`.
- `.paper-menu-popover`: hand-drawn bordered menu surface with the shared width.
  Add app positioning (`absolute`, `right`, `top`) outside the framework class.
- `.paper-menu-list`: grid wrapper for stacked menu groups.
- `.paper-menu-section`: grid group for related menu items. Adjacent sections
  receive a sketchy horizontal separator.
- `.paper-menu-section-title`: compact section label.
- `.paper-menu-item`: full-width menu action/link with PaperCSS hover, selected,
  and `aria-current` states.
- `.paper-menu-nested`: left-edge wavy vertical separator for expanded child
  panels inside menus. Prefer this over a straight `border-left`.

## Maintenance

- Do not hard-code hamburger/dropdown panel widths in downstream apps when
  `--paper-menu-popover-width` is sufficient.
- For nested menu panels, use `.paper-menu-nested` or
  `--paper-sketch-line-vertical`; avoid straight left borders.
- Update `docs/content/docs/components/dropdowns.md` and rebuild with
  `npm run css:build` after SCSS changes.
