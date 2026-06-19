---
title: Get PaperCSS2
menu: main
weight: -270
---

#### Download

PaperCSS2 fork builds are maintained from this repository. During active
development, consume the generated CSS from the fork checkout, a submodule, or a
local file dependency. The upstream `papercss` NPM package and CDN do not include
PaperCSS2 fork features.

<div class="row flex-spaces text-center">
  <a class="paper-btn margin" href="https://github.com/digix-kr/papercss2/releases">GitHub Releases</a>
  <a class="paper-btn margin" href="https://github.com/digix-kr/papercss2">GitHub Repository</a>
</div>

#### Fork checkout

Clone the fork and build the CSS artifacts:

```sh
git clone https://github.com/digix-kr/papercss2.git
cd papercss2
npm install
npm run css:build
```

Then import one of the generated files:

- dist/paper.css
- dist/paper.min.css

#### Local package

When using the fork from another project during active development, use a local
file dependency:

```json
{
  "dependencies": {
    "papercss2": "file:./packages/papercss2"
  }
}
```

Then import the built CSS:

```js
import "papercss2/dist/paper.css";
```

#### Upstream baseline

If you only need upstream PaperCSS 1.9.2 without fork features, install or link
the upstream package:

- [https://unpkg.com/papercss@1.9.2/dist/paper.css](https://unpkg.com/papercss@1.9.2/dist/paper.css)
- [https://unpkg.com/papercss@1.9.2/dist/paper.min.css](https://unpkg.com/papercss@1.9.2/dist/paper.min.css)

Here's a quick local snippet to get started with a built PaperCSS2 file:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="./dist/paper.min.css" />
    <title>Document</title>
  </head>
  <body>
    <div class="paper container">
      <h1>Some Fresh Title</h1>
      <p>This is where some content would go.</p>
    </div>
  </body>
</html>
```

#### Build it Yourself

If you'd rather customize things, build the CSS yourself via the git repo:

```sh
git clone https://github.com/digix-kr/papercss2.git
cd papercss2
npm install
npm run build
```

Grab the CSS out of the /dist folder created

You can also go into src/core/\_config.scss before building to change around the global styles of your new CSS.
