# @Intent
- Build_tooling => compile SCSS assets and Hugo docs through npm scripts.
- Watcher_flow => detect `src/**/*.scss` changes and regenerate docs CSS quickly.
- Dependency_policy => keep watcher dependency updates semver-compatible before using overrides.

# @Invariants
- Build_contract => `npm run build` must complete css build and Hugo docs build without manual steps.
- Watch_contract => `npm run dev:hot-reload` must react to SCSS file changes.
- Watch_scope => watcher input remains `src/**/*.scss` unless docs state otherwise.
- Dependency_scope => `fsevents` stays transitive_optional_only | no direct app dependency.
- Change_scope => tooling dependency fixes must not alter published CSS semantics intentionally.

# @Perf_Scale
- Dev_feedback => watch responsiveness matters more than minimizing optional macOS-only packages.
- Optional_native_dep => macOS watcher dependency can change if build and watch behavior stay stable.

# @Checklist
- Read `docs/info-rules.md` before build tooling edits.
- Update lockfiles through npm commands | no manual lockfile surgery.
- Verify installed watcher tree with `npm ls chokidar fsevents`.
- Run `npm run build` after dependency updates.
- Run hot-reload flow and confirm SCSS change detection before merge.
