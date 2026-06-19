# Paper Themes

PaperCSS2 exposes surface palette tokens through `src/core/_config.scss` and
theme classes in `src/utilities/_paper-themes.scss`.

## Public Surface

- `.paper-theme-postit` maps Post-it-specific variables into generic
  `--paper-theme-*` variables and updates `--main-background` plus
  `--main-background-light`.
- Post-it colors are maintained as SCSS defaults named
  `$paper-theme-postit-*`; the build emits matching CSS custom properties named
  `--paper-theme-postit-*`.
- Downstream apps can consume the Post-it tokens directly for app-specific
  surfaces, or apply `.paper-theme-postit` for a generic PaperCSS surface.

## Maintenance

- Keep app-specific Post-it palettes aligned with the emitted
  `--paper-theme-postit-*` tokens instead of duplicating raw colors.
- Update `docs/content/docs/utilities/paper-themes.md` when adding, renaming, or
  removing a theme token.
- Rebuild with `npm run css:build` after changing theme SCSS variables or
  utility classes.
