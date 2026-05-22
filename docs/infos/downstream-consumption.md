# Downstream Consumption

This fork is expected to be edited while another project consumes the generated
PaperCSS output.

## Recommended Active Development Setup

For frequent local edits, vendor this repository inside the consuming project
and reference it as a local file dependency.

Example structure:

```text
consumer-project/
  package.json
  packages/
    papercss/
      package.json
      src/
      dist/
```

Consumer `package.json`:

```json
{
  "dependencies": {
    "papercss": "file:./packages/papercss"
  },
  "scripts": {
    "build:papercss": "npm --prefix packages/papercss run css:build"
  }
}
```

Consumer import:

```js
import "papercss/dist/paper.css";
```

## Important Constraint

Consumers should import built CSS from `dist/`, not SCSS source files.
After editing `packages/papercss/src/**/*.scss`, rebuild:

```bash
npm --prefix packages/papercss run css:build
```

## Alternative

Use a Git submodule instead of vendoring when the PaperCSS fork must keep its
own independent history. Use plain vendoring when the fork is effectively part
of the consuming project.
