# Agent Instructions

This repository uses a small, explicit documentation system for AI coding agents.
Keep always-loaded instructions short. Put project-specific details in
`.docs/index.md` and task-specific capsules under `.docs/infos/`.

## Required Context Flow

- Before implementation, read `.docs/index.md`.
- Use `.docs/index.md` to choose only the `.docs/infos/` capsules relevant to the task.
- Do not read every capsule by default.
- If a capsule is missing for a task area, inspect the source first, then create or update the smallest useful capsule.
- If docs and source disagree, treat source code and build configuration as the behavioral truth, then update the docs to remove the mismatch.

## Documentation Maintenance

- Maintain `.docs/index.md` as the routing table for agent-readable capsules.
- Maintain `.docs/infos/` capsules when a change adds, removes, or meaningfully changes architecture, workflows, build steps, conventions, or known pitfalls.
- Keep capsules concise, concrete, and verifiable. Avoid generic coding advice.
- Prefer adding links to exact files, commands, and ownership boundaries over prose summaries.
- Do not duplicate README-style or generated site content unless it contains agent-critical guidance.

## Project Handling

- Keep changes scoped to the user's request.
- Use existing project patterns before introducing new structure.
- For PaperCSS source changes, edit `src/**/*.scss` and rebuild generated CSS with `npm run css:build` when the generated `dist/` output is part of the requested result.
- Only run tests or full builds when they are clearly needed to validate the change.
- Do not overwrite unrelated user changes.

## Completion

- At final completion of a user request, commit and push relevant changes when working inside this Git repository.
- Send exactly one Discord completion notification after the full request is complete.
