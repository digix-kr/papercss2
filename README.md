<p align="center">
  <a href="https://papercss.digix.kr">
    <img src="docs/static/favicon.ico" alt="PaperCSS2 logo">
  </a>

  <h3 align="center">PaperCSS2</h3>

  <p align="center">The less formal CSS framework, maintained as a fork for product-focused paper UI.</p>
</p>

## Table of contents

- [Table of contents](#table-of-contents)
- [PaperCSS2 fork notes](#papercss2-fork-notes)
- [Quick-start](#quick-start)
- [Content of the framework](#content-of-the-framework)
- [Documentation](#documentation)
- [Customizing](#customizing)
- [Contributing](#contributing)
- [About](#about)
- [Resources](#resources)
- [Credits and license](#credits-and-license)

## PaperCSS2 fork notes

PaperCSS2 is a fork of [PaperCSS](https://github.com/papercss/papercss).
The upstream README below is still useful for the base framework, but this
section records fork-specific changes that downstream users and maintainers
need to know.

Current fork baseline:

- Upstream base: `papercss/papercss` `master` at `b341c16`, package version `1.9.2`.
- Fork remote: `digix-kr/papercss2`.
- Embedded consumer: `meteorai-papercss` vendors this fork at
  `imports/vendor/papercss2/` and imports the built CSS from `dist/paper.css`.

Current fork usage:

- Treat this fork as the source for generated PaperCSS2 CSS in downstream apps;
  do not assume the upstream `papercss` npm package or CDN includes these
  changes.
- In package-based contexts, use the fork package name `papercss2`. The upstream
  `papercss` package remains the unmodified PaperCSS baseline.
- Downstream apps should import built CSS from `dist/paper.css`, not SCSS source
  files.
- After SCSS changes, rebuild with `npm run css:build` in this fork. From
  `meteorai-papercss`, use `npm run build:papercss2`.

Current fork changes:

- Added AI-agent documentation entrypoints: `AGENTS.md`, `docs/index.md`, and
  `docs/infos/`. These files guide development agents and are separate from
  the Hugo documentation site under `docs/content/`.
- Updated fork-owned documentation links and release guidance so fork docs point
  at `digix-kr/papercss2` where ownership matters.
- Added reusable PaperCSS form select treatment for native `select` controls,
  including custom caret styling, hover/focus states, `.paper-select-wrapper`,
  and `.paper-select-icon`.
- Added reusable JavaScript-controlled dropdown styles: `.paper-dropdown`,
  `.paper-dropdown-trigger`, `.paper-dropdown-menu`, `.paper-dropdown-item`,
  `.paper-dropdown-open`, and `.paper-dropdown-item-selected` /
  `aria-selected="true"` support.
- Added compact app menu popover styles: `--paper-menu-popover-width`,
  `.paper-menu-popover`, `.paper-menu-list`, `.paper-menu-section`,
  `.paper-menu-section-title`, `.paper-menu-item`, and `.paper-menu-nested`
  for hamburger/dropdown menus with consistent width and hand-drawn nested
  separators.
- Added a reusable hand-drawn text-link underline mixin and applied it to
  content links while keeping `.paper-btn`, modal actions, and button-like links
  free of text-link underline artwork.
- Added reusable profile summary card styles: `.paper-profile-card`,
  `.paper-profile-card-header`, `.paper-profile-card-kicker`,
  `.paper-profile-card-title`, `.paper-profile-card-meta`,
  `.paper-profile-card-body`, and `.paper-profile-card-bio`.
- Refined dropdown selected-item fill so active and hovered menu items keep an
  inset, hand-drawn PaperCSS shape.
- Added hand-drawn dividers: a `.paper-divider` element, a `--paper-sketch-line`
  custom property (so apps can draw their own separators without redrawing the
  SVG), the `paper-sketch-line` / `paper-sketch-line-url` SCSS helpers, and a
  compact `.border-soft` wobble (border style 7) for small boxes such as chips,
  counters, and list notes.
- Replaced the straight `.paper-profile-card-header` bottom border with the
  hand-drawn sketch line so the header/body split reads as PaperCSS.
- Added PaperCSS2 text-selection highlights with CSS custom properties and
  preset classes: `.paper-selection-paper-marker`,
  `.paper-selection-blue-pencil`, and `.paper-selection-rose-correction`.
- Added brushed text-selection overlay classes (`.paper-selection-brushed`,
  `.paper-selection-brush-layer`, `.paper-selection-brush-mark`) so downstream
  apps can render hand-painted highlighter edges without showing the native
  rectangular selection fill.
- Added a hand-drawn quote bar: a `.paper-quote` class, a
  `--paper-sketch-line-vertical` custom property, and the
  `paper-sketch-line-vertical` / `paper-sketch-line-vertical-url` SCSS helpers,
  so quoted/shared content uses a wavy vertical stroke on its left edge instead
  of a ruler-straight `border-left`.
- Changed the default PaperCSS2 body and heading fonts to `Poor Story` so
  Latin and Korean text share the same handwritten face by default.
- Added Post-it paper theme tokens and `.paper-theme-postit`, which maps
  `--paper-theme-postit-*` values into generic `--paper-theme-*` variables for
  app shells, headers, menus, surfaces, hover states, and borders.
- Added notebook-style page backgrounds with `.paper-note-lines`,
  `--paper-note-lines-*` runtime tokens, and the `paper-note-lines` /
  `paper-note-lines-url` SCSS helpers.

Maintenance rule:

- When a fork change affects downstream usage, available CSS classes,
  generated CSS behavior, docs ownership, or release/installation workflow,
  add a concise bullet to this section in the same change.
- Keep `docs/index.md` and `docs/infos/` focused on agent-readable development
  guidance. They can explain when to update this README, but they should not
  replace this user-facing fork change log.
- Keep Hugo user documentation under `docs/content/` focused on component usage
  examples and site content.

## Quick-start

There are several fork-safe options available:

- Download fork release assets from
  [GitHub Releases](https://github.com/digix-kr/papercss2/releases) when a
  release has been published.
- Clone the fork directly: `git clone https://github.com/digix-kr/papercss2.git`
- Use it as a submodule or local file dependency while the fork is evolving.
- Import the generated CSS from this fork:
  - `dist/paper.css`
  - `dist/paper.min.css`
- If you intentionally want upstream PaperCSS without PaperCSS2 fork features,
  use `npm install papercss` or the upstream `unpkg.com/papercss` CDN URLs.

## Content of the framework

We provide compiled CSS (`paper.css`) as well as minified CSS (`paper.min.css`).

You can choose which components you may want to use. Only the components that get imported into `src/styles.scss` will be compiled into `dist/paper.css`.

You can also play with original, source files, written in SCSS, in `src/`.

## Documentation

The fork docs are configured for [papercss.digix.kr](https://papercss.digix.kr)
and are built from this repository. For local docs, run `npm run dev` and open
the Hugo server URL printed by the command.

## Customizing

You can customize PaperCSS easily, clone the repo, run `npm install` and make any changes to `.scss` files in `src/`.

The main place you might want to make changes would be `core/_config.scss`, where you can specify new colors or fonts for your CSS build.

After you make changes, be sure to build the new CSS files. Do so by running `npm run css:build` and get them from the `dist/` folder.

## Contributing

This project is open source and contributions are very welcomed. It is also as beginner friendly as possible, so don't be afraid to jump in if you've never contributed to any Git project before! Feel free to reach out if you are new and need help with the process.

Please before sending a PR, make sure you are properly using the `.editorconfig` file with your IDE. If your IDE doesn't natively support `editorconfig` files, you can use an extension/package/module. For example in Atom there is the [editorconfig package](https://atom.io/packages/editorconfig), as well for [Sublime Text](https://github.com/sindresorhus/editorconfig-sublime), [VS Code](https://github.com/editorconfig/editorconfig-vscode), [Vim](https://github.com/editorconfig/editorconfig-vim), ...

Once you are ready to contribute to this fork, use this workflow:

- Fork the repo then clone it: `git clone git@github.com:[your_username]/papercss2.git`
- `cd papercss2` then install dependencies: `npm install`
- Create your new branch from `main`: `git checkout -b feature-thing main`.
- Write some code!
- To build the scss (in `src/`) to css (in `dist/`), run `npm run css:build`. Note: you will need to re-run this command to include the latest changes in `src/`.
- To preview your changes, you can run `npm start`. This will start a `localhost` server.
- Check to make sure your code is following style rules with `npm run stylelint`
- Once done commit and push your changes to your fork. The linter is also run as a pre-commit hook.
- Open a pull request against `digix-kr/papercss2`.

## About

PaperCSS was originally made by [@rhyneav](https://github.com/rhyneav) to be something different than the typical mODerN STylEs and clean pages found in every other CSS framework. It was built with LESS and deployed on a single index.html page before being open sourced. It has since evolved; the CSS source has been rewritten in SCSS and the documentation is now built with Hugo. PaperCSS2 is maintained by [@digix-kr](https://github.com/digix-kr) as a fork with product-focused paper UI additions.

The goal of PaperCSS is to be as minimal as possible when adding classes. For example, a button should just look like a paper button. There shouldn't be a need to add a class such as `paper-button`. Because of this, adding PaperCSS to a markdown generated page should instantly paper-ize it.

Feel free to use it for wireframes, web apps, blogs, or whatever else you can think of!

If you are new to Git or SCSS, this remains a good project to learn with because the CSS source, generated output, and docs live in one small repository.

## Resources

Components:

- [react-papercss-design](https://hacker0limbo.github.io/react-papercss-design/en-US) a React component library based on PaperCSS
- [Spaper](https://oli8.github.io/spaper/) PaperCSS components for Svelte
- [vue-papercss](https://github.com/papercss/vue-papercss) A vue-plugin for the less formal CSS framework
- [RailsPapercss](https://github.com/papercss/rails_papercss_gem) Rails gem for Papercss framework
- [react-native-paper-css](https://github.com/papercss/react-native-paper-css) PaperCSS for react-native
- [React PaperCSS](https://papercss.github.io/React-Paper-CSS-Page/) Another react component library implementation for PaperCSS

Icons:

- [handdrawn.css](https://fxaeberhard.github.io/handdrawn.css/) Another hand-drawn css library with rich icons included
- [hand-drawn-icons](https://github.com/nikhilol/hand-drawn-icons) Icon pack with a hand-drawn style

## Credits and license

Code and documentation under the [ISC license](LICENSE.md).

Shout out to Tiffany Rayside for creating Imperfect Buttons, which was an inspiration for this project. https://codepen.io/tmrDevelops/pen/VeRvKX
