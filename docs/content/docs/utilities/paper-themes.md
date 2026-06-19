---
title: Paper Themes
description: PaperCSS surface color themes
---

PaperCSS2 exposes paper surface tokens for products that want coordinated page
backgrounds, panels, menu surfaces, and borders.

### Post-it theme

Apply the class to `html`, `body`, or a scoped wrapper:

```html
<html class="paper-theme-postit">
```

The class maps the Post-it token set into generic `--paper-theme-*` variables
and updates `--main-background` plus `--main-background-light`:

```css
.paper-theme-postit {
  --paper-theme-surface: var(--paper-theme-postit-surface);
  --paper-theme-border: var(--paper-theme-postit-border);
}
```

Available Post-it tokens:

- `--paper-theme-postit-body-background`
- `--paper-theme-postit-shell-background`
- `--paper-theme-postit-header-background`
- `--paper-theme-postit-mobile-band-background`
- `--paper-theme-postit-menu-background`
- `--paper-theme-postit-surface`
- `--paper-theme-postit-surface-strong`
- `--paper-theme-postit-surface-plain`
- `--paper-theme-postit-surface-soft`
- `--paper-theme-postit-surface-muted`
- `--paper-theme-postit-hover-surface`
- `--paper-theme-postit-border`
- `--paper-theme-postit-border-light`
- `--paper-theme-postit-border-counter`

Override the SCSS variables in `src/core/_config.scss` before building, or set
the CSS custom properties downstream for product-specific palettes.
