<!-- Copilot / AI Agent instructions for the `expanding-search-bar-using-focus-within` demo -->

# Copilot instructions

This repository is a tiny, static front-end demo that showcases an expanding search input using the CSS `:focus-within` pattern. The goal of AI edits should be to preserve the small, dependency-free nature of the project and follow the existing class and SCSS conventions.

**Big picture**

- **Purpose:** Single-page demo. No JS frameworks. Primary interaction is CSS-driven expansion of the search bar.
- **Key files:** `index.html` (markup), `css/main.scss` (source styles), `css/main.css` (built CSS), `assets/` (icons/assets).
- **Core pattern:** The component uses a block/element class naming (`.search-bar`, `.search-bar__input`, `.search-bar__submit`) and relies on a `:focus-within` rule in `css/main.scss` to expand the wrapper and reveal the input.

**What to change (and how) — actionable rules for the agent**

- Preserve the single-file, static-site approach. Avoid adding heavy build tools, frameworks, or production optimizations unless the user asks.
- Keep the BEM-like naming used in `css/main.scss`: modify or add classes following the `block__element` pattern (e.g., add `.search-bar__icon` rather than `icon-search`).
- When editing styles, modify `css/main.scss`. The repository uses SCSS source; do not edit `css/main.css` directly unless you also update `main.scss`.
- When changing behavior, prefer CSS-first solutions (pseudo-classes, transitions). Only add JavaScript if the feature cannot be done with CSS; if adding JS, create a minimal file (e.g., `js/behavior.js`) and reference it in `index.html`.

**Local developer workflow / commands**

- This repo has no build system configured. Typical dev steps:

  - Compile SCSS to CSS (if you edit `main.scss`):

    ```powershell
    # Using Dart Sass (install via npm or https://sass-lang.com/install)
    sass --watch "css/main.scss":"css/main.css"
    ```

  - Serve the demo locally (pick one):

    ```powershell
    # Quick static server via Node (install http-server globally or use npx)
    npx http-server -c-1

    # or Python 3 simple server
    python -m http.server 8000
    ```

  - Alternatively, open `index.html` directly in a browser for basic testing.

**Patterns and examples from the codebase**

- Expanding search pattern (see `css/main.scss`):

  - Block: `.search-bar`
  - Elements: `.search-bar__input`, `.search-bar__submit`
  - Key selector: `.search-bar:focus-within { width: 100%; /* ... */ }`

- Markup example (from `index.html`):

  ```html
  <div class="search-bar">
    <input class="search-bar__input" placeholder="Search" />
    <button class="search-bar__submit">...</button>
  </div>
  ```

**Conventions specific to this repo**

- SCSS variables are defined at `:root` within `main.scss` (e.g., `--clr-primary`). Prefer using those variables where possible.
- Transition timings and sizes use CSS custom properties inside `.search-bar` (`--size`) — prefer adjusting those over hardcoding numbers in multiple places.
- Avoid introducing new global resets or layout changes; the demo intentionally centers a single card (`.content`) for visual clarity.

**Integration points / external deps**

- The page loads Material Icons from Google Fonts in `index.html`. Keep that link if edits rely on the same icons.
- No JS libraries, package.json, or CI scripts are present — don't assume npm or other toolchains are available unless the user asks to add them.

**When to open a PR vs commit directly**

- Prefer opening a PR for any change that affects behavior, accessibility, or public-facing markup/styles. Small formatting or comment-only edits can be committed directly if requested.

**Safety and accessibility notes**

- If adding interactive behavior, ensure keyboard accessibility (e.g., focus states on the submit button, inputs reachable by Tab).
- Keep color contrast reasonable when changing `--clr-primary` or button colors.

If anything in this summary is unclear or you'd like me to include additional examples (unit tests, a `package.json`, or CI steps), tell me which areas to expand and I'll iterate.
