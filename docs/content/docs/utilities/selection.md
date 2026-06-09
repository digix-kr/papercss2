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

### Brushed marker overlay

Native `::selection` is painted by the browser and only accepts a small set of
styles, so it cannot draw wobbly marker edges by itself. For a hand-painted
selection, add `.paper-selection-brushed` to make the native rectangular fill
transparent, then render selection rectangles with PaperCSS2's overlay classes:

```html
<html class="paper-selection-paper-marker paper-selection-brushed">
  <div class="paper-selection-brush-layer" aria-hidden="true">
    <span
      class="paper-selection-brush-mark"
      style="
        --paper-selection-brush-left: 10px;
        --paper-selection-brush-top: 20px;
        --paper-selection-brush-width: 140px;
        --paper-selection-brush-height: 18px;
        --paper-selection-brush-rotate: -0.6deg;
      "
    ></span>
  </div>
</html>
```

The overlay mark uses the active preset's `--paper-selection-background`, so
switching from Paper Marker to Blue Pencil or Rose Correction changes both the
native fallback and the brushed overlay.
