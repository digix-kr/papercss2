---
title: Borders & Shadows
slug: borders
description: PaperCSS Borders & Shadows
---
### Borders

<div class="row flex-spaces">
  <div class="sm-3 col border border-primary">Default Border</div>
  <div class="sm-3 col border border-2 border-primary">Border-2</div>
  <div class="sm-3 col border border-3 border-primary">Border-3</div>
</div>
<div class="row flex-spaces">
  <div class="sm-3 col border border-4 border-primary">Border-4</div>
  <div class="sm-3 col border border-5 border-primary">Border-5</div>
  <div class="sm-3 col border border-6 border-primary">Border-6</div>
</div>
<div class="row flex-spaces">
  <div class="sm-3 col border border-soft border-primary">Border Soft</div>
  <div class="sm-3 col border border-7 border-primary">Border-7</div>
</div>

#### Code:

```html
<div class="row flex-spaces">
  <div class="sm-3 col border border-primary">Default Border</div>
  <div class="sm-3 col border border-2 border-primary">Border-2</div>
  <div class="sm-3 col border border-3 border-primary">Border-3</div>
</div>
<div class="row flex-spaces">
  <div class="sm-3 col border border-4 border-primary">Border-4</div>
  <div class="sm-3 col border border-5 border-primary">Border-5</div>
  <div class="sm-3 col border border-6 border-primary">Border-6</div>
</div>
<div class="row flex-spaces">
  <div class="sm-3 col border border-soft border-primary">Border Soft</div>
  <div class="sm-3 col border border-7 border-primary">Border-7</div>
</div>
```

Use `.border-soft` or `.border-7` when a compact item needs a softer wobble
than the larger border shapes.

### Border Colors

<div class="row child-borders">
  <div class="sm-2 col border border-primary">Border primary</div>
  <div class="sm-2 col border border-secondary">Border secondary</div>
  <div class="sm-2 col border border-success">Border success</div>
  <div class="sm-2 col border border-warning">Border warning</div>
  <div class="sm-2 col border border-danger">Border danger</div>
  <div class="sm-2 col border border-white">Border white</div>
</div>

#### Code:

```html
<div class="row child-borders">
  <div class="sm-2 col border border-primary">Border primary</div>
  <div class="sm-2 col border border-secondary">Border secondary</div>
  <div class="sm-2 col border border-success">Border success</div>
  <div class="sm-2 col border border-warning">Border warning</div>
  <div class="sm-2 col border border-danger">Border danger</div>
  <div class="sm-2 col border border-white">Border white</div>
</div>
<div class="row child-borders">
  <div class="sm-2 col border border-primary">Border primary</div>
  <div class="sm-2 col border border-secondary">Border secondary</div>
  <div class="sm-2 col border border-success">Border success</div>
  <div class="sm-2 col border border-warning">Border warning</div>
  <div class="sm-2 col border border-danger">Border danger</div>
  <div class="sm-2 col border border-white">Border white</div>
</div>
```

### Child Borders

Use this if you want all children to have a border. This will alternate through the different border styles defined above instead of having to add the border class for each element.

<div class="row flex-center child-borders">
  <div class="sm-2 col">1</div>
  <div class="sm-2 col">2</div>
  <div class="sm-2 col">3</div>
  <div class="sm-2 col">4</div>
  <div class="sm-2 col">5</div>
  <div class="sm-2 col">6</div>
</div>

#### Code:

```html
<div class="row flex-center child-borders">
  <div class="sm-2 col">1</div>
  <div class="sm-2 col">2</div>
  <div class="sm-2 col">3</div>
  <div class="sm-2 col">4</div>
  <div class="sm-2 col">5</div>
  <div class="sm-2 col">6</div>
</div>
```

### Border Styles

<div class="row flex-spaces child-borders">
  <div class="sm-3 col border-dashed">Dashed</div>
  <div class="sm-3 col border-dotted">Dotted</div>
  <div class="sm-3 col border-dashed border-thick">Dashed Thick</div>
  <div class="sm-3 col border-dotted border-thick">Dotted Thick</div>
</div>

#### Code:

```html
<div class="row flex-spaces child-borders">
  <div class="sm-3 col border-dashed">Dashed</div>
  <div class="sm-3 col border-dotted">Dotted</div>
  <div class="sm-3 col border-dashed border-thick">Dashed Thick</div>
  <div class="sm-3 col border-dotted border-thick">Dotted Thick</div>
</div>
```

### Hand-drawn Dividers

Use `.paper-divider` when you want a wavy PaperCSS separator instead of a
straight border line. `.paper-divider-tight` reduces vertical spacing and
`.paper-divider-faint` lowers the contrast for dense lists.

<div class="docs-divider-demo">
  <p>Section one</p>
  <hr class="paper-divider">
  <p>Section two</p>
  <hr class="paper-divider paper-divider-tight paper-divider-faint">
  <p>Dense note or comment separator</p>
</div>

#### Code:

```html
<p>Section one</p>
<hr class="paper-divider">
<p>Section two</p>
<hr class="paper-divider paper-divider-tight paper-divider-faint">
<p>Dense note or comment separator</p>
```

For existing block edges, reuse the exported sketch-line custom properties:

```css
.my-section {
  background: var(--paper-sketch-line) repeat-x bottom center / 3.2em 0.5em;
}

.my-compact-list-item + .my-compact-list-item {
  background: var(--paper-sketch-line-faint) repeat-x top center / 3.2em 0.5em;
}
```

### Quote Bar

Use `.paper-quote` for quoted or shared content that should have a hand-drawn
vertical stroke instead of a straight `border-left`.

<blockquote class="paper-quote docs-quote-demo">
  This quoted note uses the same vertical sketch stroke token that downstream
  apps can reuse through <code>--paper-sketch-line-vertical</code>.
</blockquote>

#### Code:

```html
<blockquote class="paper-quote">
  This quoted note uses the same vertical sketch stroke token.
</blockquote>
```

### Shadows

<div class="row flex-spaces child-borders">
  <div class="sm-3 col shadow shadow-large">Large</div>
  <div class="sm-3 col shadow">Default</div>
  <div class="sm-3 col shadow shadow-small">Small</div>
  <div class="sm-3 col shadow shadow-hover">Hover</div>
</div>

#### Code:

```html
<div class="row flex-spaces child-borders">
  <div class="sm-3 col shadow shadow-large">Large</div>
  <div class="sm-3 col shadow">Default</div>
  <div class="sm-3 col shadow shadow-small">Small</div>
  <div class="sm-3 col shadow shadow-hover">Hover</div>
</div>
```

### Child Shadows

Use this if you want all children to have a shadow.

<div class="row flex-spaces child-borders child-shadows">
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col shadow-none">No Shadow</div>
</div>

#### Code:

```html
<div class="row flex-spaces child-borders child-shadows">
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col shadow-none">No Shadow</div>
</div>
```

### Child Shadows Hover

Use this if you want all children to have a shadow... that changes on hover

<div class="row flex-spaces child-borders child-shadows-hover">
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col">Shadow</div>
</div>

#### Code:

```html
<div class="row flex-spaces child-borders child-shadows-hover">
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col">Shadow</div>
  <div class="sm-3 col">Shadow</div>
</div>
```
