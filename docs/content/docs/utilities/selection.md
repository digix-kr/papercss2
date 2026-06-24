---
title: Selection
description: PaperCSS text selection highlights
---

PaperCSS2 gives selected text a paper-first highlight instead of the browser
default. The default preset is `paper-marker`: a pale marker stroke with dark
ink text.

### Presets

Apply a preset class to `html`, `body`, or a scoped container:

<div class="docs-selection-preview">
  <div class="paper-selection-paper-marker docs-selection-sample">
    <strong>Paper marker</strong>
    <p>Drag text in a scoped container, or use <span class="docs-selection-highlight">the same token values</span> in custom UI.</p>
  </div>
  <div class="paper-selection-blue-pencil docs-selection-sample">
    <strong>Blue pencil</strong>
    <p>Use <span class="docs-selection-highlight">cooler correction marks</span> for product surfaces that need a blue cue.</p>
  </div>
  <div class="paper-selection-rose-correction docs-selection-sample">
    <strong>Rose correction</strong>
    <p>Use <span class="docs-selection-highlight">warm editorial marks</span> for review and annotation flows.</p>
  </div>
</div>

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
  --paper-selection-background: #ffdc63;
  --paper-selection-color: #2f2924;
  --paper-selection-native-background: #ffdc63;
}
```

Available preset tokens:

- `--paper-selection-paper-marker-background`
- `--paper-selection-paper-marker-color`
- `--paper-selection-blue-pencil-background`
- `--paper-selection-blue-pencil-color`
- `--paper-selection-rose-correction-background`
- `--paper-selection-rose-correction-color`

`--paper-selection-native-background` controls the browser's native rectangular
`::selection` fill. Leave it aligned with `--paper-selection-background` for
normal selection, or make it transparent through `.paper-selection-brushed` when
an app renders its own brush marks.

### Brushed marker overlay

Native `::selection` is painted by the browser and only accepts a small set of
styles, so it cannot draw wobbly marker edges by itself. For a hand-painted
selection, add `.paper-selection-brushed` to make the native rectangular fill
transparent, then render selection rectangles with PaperCSS2's overlay classes:

<div class="paper-selection-paper-marker docs-selection-brush-preview">
  <p>This static preview uses the same brush mark class that an app would position over selected text.</p>
  <div class="paper-selection-brush-layer" aria-hidden="true">
    <span
      class="paper-selection-brush-mark"
      style="
        --paper-selection-brush-left: 8px;
        --paper-selection-brush-top: 30px;
        --paper-selection-brush-width: 22rem;
        --paper-selection-brush-height: 18px;
        --paper-selection-brush-rotate: -0.6deg;
      "
    ></span>
  </div>
</div>

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

Tune the overlay size with these optional tokens:

```css
:root {
  --paper-selection-brush-opacity: 0.84;
  --paper-selection-brush-height-scale: 1.17;
  --paper-selection-brush-min-height: 13px;
  --paper-selection-brush-horizontal-bleed: 3px;
}
```

Use one painted layer at a time: `.paper-selection-brushed` makes native
selection transparent, and the runtime should render only
`.paper-selection-brush-mark` elements. iOS Safari does not support styling
native text selection with `::selection`; products should skip brushed overlays
there and allow the browser default.
