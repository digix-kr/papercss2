# Build Workflow

PaperCSS source styles live under `src/` and are compiled into distributable CSS
under `dist/`.

## CSS Build

Use:

```bash
npm run css:build
```

This runs `build/build.js`, which:

- removes and recreates `dist/`
- compiles `src/styles.scss`
- runs autoprefixer
- runs cssnano for the minified output
- writes `dist/paper.css`
- writes `dist/paper.min.css`
- writes `docs/static/assets/paper.css` when the docs path exists

## Watcher Caveat

`npm run dev:hot-reload` uses `build/hot-reload.js`.

That watcher writes docs CSS only. It does not update `dist/paper.css`.
When downstream projects import `papercss/dist/paper.css`, use
`npm run css:build` after SCSS changes unless a dedicated dist watcher is added.

## Full Build

Use:

```bash
npm run build
```

This builds CSS and the Hugo documentation site. Do not run it unless docs output
or full project validation is relevant to the task.
