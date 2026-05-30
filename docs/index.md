# Agent Documentation Index

This file is the first stop for AI coding agents working in this repository.
Use it to decide which focused capsule under `docs/infos/` is relevant. Do not
load every capsule by default.

## How To Use This Index

- Read this file before implementation work.
- Open only the capsules that match the current task.
- If no capsule matches, inspect the code directly and add a concise capsule only when the finding is likely to matter again.
- Update this index whenever a capsule is added, renamed, removed, or its scope changes.

## Document Types In `docs/`

- `docs/content/`, `docs/layouts/`, `docs/static/`, and `docs/config.toml` are
  Hugo user documentation for PaperCSS components and the public docs site.
- `docs/index.md` and `docs/infos/` are AI-agent development guides. They are
  intentionally stored beside the Hugo docs because both describe this fork,
  but they have a different audience and should stay operational.
- `README.md` is the fork-facing entrypoint and change log for downstream
  users. Consumer-visible fork changes should be recorded there first, with
  `docs/infos/` updated only when agents need durable workflow or architecture
  guidance for future work.

## Capsule Directory

Capsules live in `docs/infos/`.

Current capsules:

- `docs/infos/README.md`: Capsule writing rules and maintenance expectations.
- `docs/infos/build-workflow.md`: CSS build outputs and command behavior.
- `docs/infos/downstream-consumption.md`: Recommended way to consume this fork from another project during active development.
- `docs/infos/fork-readme-maintenance.md`: README fork change-log ownership and update triggers.
- `docs/infos/release-policy.md`: Release-time documentation update checklist for this fork.

## Project Map

- `src/styles.scss`: SCSS entrypoint for PaperCSS.
- `src/core/`: Core reset, configuration, and mixins.
- `src/content/`: Base content styles such as typography, lists, tables, images, fonts, and code.
- `src/components/`: Component styles such as buttons, dropdowns, forms, cards, tabs, modals, navbar, alerts, and utilities.
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
- A fork change should keep being recorded in `README.md` and agents need a repeatable rule for doing it.
- Source organization changes in a way future agents should know.
- A repeated agent mistake reveals a missing project rule.
- A downstream integration pattern becomes the recommended way to consume this fork.

Do not update capsules for trivial implementation details that are obvious from nearby source code.
