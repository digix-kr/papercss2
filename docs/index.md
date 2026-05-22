# Agent Documentation Index

This file is the first stop for AI coding agents working in this repository.
Use it to decide which focused capsule under `docs/infos/` is relevant. Do not
load every capsule by default.

## How To Use This Index

- Read this file before implementation work.
- Open only the capsules that match the current task.
- If no capsule matches, inspect the code directly and add a concise capsule only when the finding is likely to matter again.
- Update this index whenever a capsule is added, renamed, removed, or its scope changes.

## Capsule Directory

Capsules live in `docs/infos/`.

Current capsules:

- `docs/infos/README.md`: Capsule writing rules and maintenance expectations.
- `docs/infos/build-workflow.md`: CSS build outputs and command behavior.
- `docs/infos/downstream-consumption.md`: Recommended way to consume this fork from another project during active development.

## Project Map

- `src/styles.scss`: SCSS entrypoint for PaperCSS.
- `src/core/`: Core reset, configuration, and mixins.
- `src/content/`: Base content styles such as typography, lists, tables, images, fonts, and code.
- `src/components/`: Component styles such as buttons, forms, cards, tabs, modals, navbar, alerts, and utilities.
- `src/layout/`: Layout helpers such as container and flexbox.
- `src/utilities/`: Border and shadow utilities.
- `build/build.js`: CSS build script that compiles SCSS, runs autoprefixer/cssnano, and writes `dist/paper.css`, `dist/paper.min.css`, and docs CSS.
- `build/hot-reload.js`: Development watcher for docs CSS, not the main `dist/` output.
- `dist/`: Built CSS artifacts consumed by downstream projects.
- `docs/content/`: Hugo documentation site content. This is separate from agent capsules in `docs/infos/`.

## Common Commands

- Install dependencies: `npm install`
- Build CSS artifacts: `npm run css:build`
- Build full project and docs: `npm run build`
- Run docs/dev server: `npm run dev`
- Lint SCSS: `npm run lint`

## Maintenance Triggers

Update `docs/infos/` and this index when:

- A new build, release, import, or local development workflow is established.
- Source organization changes in a way future agents should know.
- A repeated agent mistake reveals a missing project rule.
- A downstream integration pattern becomes the recommended way to consume this fork.

Do not update capsules for trivial implementation details that are obvious from nearby source code.
