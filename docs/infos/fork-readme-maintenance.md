# Fork README Maintenance

The root `README.md` is the consumer-facing entrypoint for this fork. Use it to
record what changed after the upstream PaperCSS baseline and how downstream
projects should consume those changes.

## Ownership

- `README.md` owns the high-level fork change log and downstream usage notes.
- `docs/content/` owns Hugo user documentation and component examples.
- `docs/index.md` and `docs/infos/` own AI-agent guidance for future code and
  documentation work.
- Do not move agent capsule details into the README unless they affect a human
  maintainer's use of the fork.

## Update Triggers

Update `README.md` when a change affects:

- exported CSS behavior in `dist/paper.css` or `dist/paper.min.css`
- public SCSS/CSS classes expected to be used by downstream projects
- installation, import, build, release, or docs ownership workflow
- component documentation that changes how a downstream app should adopt this fork

Update `docs/index.md` or a focused `docs/infos/` capsule when a change affects
how future agents should build, test, release, document, or consume the fork.

## Boundaries

- Keep README bullets concise and user-facing; prefer feature names, class names,
  and downstream effects over implementation internals.
- Keep capsules operational; do not duplicate the full README change log inside
  `docs/infos/`.
- Keep Hugo docs under `docs/content/` focused on end-user examples and visible
  documentation pages.

## Checklist

- Add or update the fork notes in `README.md` for consumer-visible changes.
- Update Hugo docs under `docs/content/` when component usage examples changed.
- Update `docs/index.md` and the relevant capsule when future agents need the
  rule, workflow, or pitfall.
- Rebuild CSS with `npm run css:build` after SCSS changes before relying on
  `dist/` output.
