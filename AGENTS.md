# AGENTS.md

## Project Overview

This is a static travel website (HTML/CSS/JS) for a School. Pages
serve as the entry points to each feature on the site.

## Directory Structure

Each feature/page must live in its own folder inside `pages/`, and every folder
must hold its own HTML, CSS, and JS files:

```
pages/
  <feature-name>/
    <feature-name>.html
    <feature-name>.css
    <feature-name>.js
```

Example:

```
pages/
  home/
    home.html
    home.css
    home.js
  hotels/
    hotels.html
    hotels.css
    hotels.js
  destinations/
    destinations.html
    destinations.css
    destinations.js
```

## Rules

1. **Every page stays in `pages/`.** Never create a new HTML page at the repo
   root; only create pages inside a feature folder under `pages/`.

2. **One feature = one folder.** Each feature/page is scoped to its own folder.

3. **Keep feature files inside its folder.** A feature's stylesheets and scripts
   go inside that feature's own folder. Never add feature styles or scripts to
   root-level files (`home.css`, `global.css`, `script.js`) or to another
   feature's folder.

4. **Match the base filename with the folder.** A `hotels/` folder contains
   `hotels.html`, `hotels.css`, and `hotels.js`.

5. **Shared assets go to the root.** `global.css` holds global/shared styles
   (variables, reset, typography). Shared images live in `images/`. Only copy
   an image into a feature folder if it is used by that feature alone.

6. **Use root-relative paths.** Every page's `<head>` must include
   `<base href="/" />`, which makes all paths resolve from the project root.
   Never use `../` traversal. Reference assets and pages directly from the
   root: `global.css`, `images/...`, `pages/<feature>/<feature>.html`,
   `index.html`.

## Conventions

- Use kebab-case for folder and file names (e.g. `phnom-penh/`, `booking-page.css`).
- Link only the page's own CSS/JS files inside its HTML (plus `global.css`
  for shared styles), addressing them as `pages/<feature>/<feature>.css` and
  `pages/<feature>/<feature>.js`.
- Write code that matches existing patterns: BEM-style class names, CSS custom
  properties from `global.css`, and the `reveal` animation classes already used
  on the site.
- Serving: because `<base href="/" />` requires an origin, pages must be
  served over HTTP (e.g. `python -m http.server`) during development — opening
  the HTML directly via `file://` will not resolve paths.

## Navigation Links

The header in `index.html` defines the site's pages: Home, Destinations, Tours,
Hotels, About, Contact, and Login/Signup. When these pages are created, update
the header nav links to point at the corresponding `pages/<feature>/` HTML file.