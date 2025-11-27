# expanding-search-bar-using-focus-within

A tiny, dependency-free demo that showcases an expanding search input driven purely by CSS using the `:focus-within` pattern.

Demo: a centered card with a circular search control that expands when focused to reveal the input.

---

## Table of Contents

- [Description](#description)
- [Demo](#demo)
- [Installation](#installation)
- [Usage](#usage)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Description

This repo contains a single static page demonstrating a compact, accessible search component that expands using CSS only. It's intentionally small and framework-free so the interaction is easy to read and adapt.

Key files:

- `index.html` — markup for the demo.
- `css/main.scss` — source SCSS (preferred for edits).
- `css/main.css` — compiled CSS used by the page.
- `assets/expanding-search-bar-using-focus-within.mkv` — short demo video showing the component in action.

## Demo

You can preview the demo video bundled with the repo. Note: many markdown renderers and GitHub may block autoplay - a direct raw link is provided as a fallback.

<video src="assets/expanding-search-bar-using-focus-within.mkv" controls autoplay muted loop playsinline width="640">
  Your browser does not support the video tag.
</video>

- Raw / download: https://raw.githubusercontent.com/transcenddev/expanding-search-bar-using-focus-within/main/assets/expanding-search-bar-using-focus-within.mkv

Or open `index.html` directly in a browser.

## Installation

No build system or package manager is required. To edit the SCSS and preview changes you'll need a Sass compiler (Dart Sass recommended).

Compile SCSS to CSS (PowerShell example):

```powershell
# Install Dart Sass separately if you don't have it, then:
sass --watch "css/main.scss":"css/main.css"
```

Serve the folder to preview in the browser (optional):

```powershell
# Using Node's http-server via npx
npx http-server -c-1

# or Python's simple server
python -m http.server 8000
```

## Usage

- Edit `css/main.scss` to change colors, sizes, or transitions. The project follows a small BEM-like pattern: `.search-bar`, `.search-bar__input`, `.search-bar__submit`.
- Use the `--size` custom property defined on `.search-bar` to change the compact/expanded geometry consistently.

Example markup (from `index.html`):

```html
<div class="search-bar">
  <input class="search-bar__input" placeholder="Search" />
  <button class="search-bar__submit">🔍</button>
</div>
```

## Development

- Prefer CSS-first solutions: `:focus-within`, transitions, and custom properties are the primary tools.
- If you must add behavior, add a minimal `js/behavior.js` and reference it in `index.html`. Keep JS small and accessible (keyboard interaction, focus management).

## Contributing

Small changes (formatting, documentation) can be committed directly. For behavior, accessibility, or UX changes open a PR describing the change and any compatibility considerations.

## License

This project has no license file. Add one (e.g., `LICENSE` with MIT) if you want to allow reuse.
