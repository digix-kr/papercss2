---
title: Selection
description: PaperCSS text selection highlights
---

PaperCSS2 gives selected text a paper-first highlight instead of the browser
default. The default preset is `paper-marker`: a pale marker stroke with dark
ink text.

### Presets

Apply a preset class to `html`, `body`, or a scoped container:

```html
<html class="paper-selection-paper-marker">
```

```html
<html class="paper-selection-blue-pencil">
```

```html
<html class="paper-selection-rose-correction">
```

### Custom selection colors

Override the selection custom properties when a product needs its own palette:

```css
:root {
  --paper-selection-background: #fff0a8;
  --paper-selection-color: #2f2924;
}
```

Available preset tokens:

- `--paper-selection-paper-marker-background`
- `--paper-selection-paper-marker-color`
- `--paper-selection-blue-pencil-background`
- `--paper-selection-blue-pencil-color`
- `--paper-selection-rose-correction-background`
- `--paper-selection-rose-correction-color`
