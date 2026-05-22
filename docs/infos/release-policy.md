# Release Policy

This capsule defines what must be updated in docs when publishing a new release.

## Trigger

Run this checklist whenever a new tagged release is created for this fork.

## Required Updates

- Update version references in `docs/content/_index.md` for NPM and CDN examples.
- Verify `https://unpkg.com/papercss@<version>/dist/paper.css` and
  `https://unpkg.com/papercss@<version>/dist/paper.min.css` resolve.
- Ensure `GitHub Releases` button in `docs/content/_index.md` points to
  `https://github.com/digix-kr/papercss/releases`.
- If direct release asset buttons are reintroduced, ensure URLs target this fork
  and the current tag.

## Optional Updates

- Add release notes link references in docs pages that mention "latest version".
- Refresh code snippets if entrypoint or package usage changed.
