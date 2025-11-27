# expanding-search-bar-using-focus-within

Minimal, accessible CSS-only expanding search bar demo.

What it is

- Single static page showing a circular search button that expands to an input using `:focus-within`.

Play the demo (may require clicking the thumbnail on GitHub):

<video src="assets/Expanding-Search-Bar-Using-Focus-Within.mp4" controls muted loop playsinline width="640">
  Your browser does not support the video tag.
</video>

Quick start

- Open `index.html` in a browser.
- To edit styles: run `sass --watch "css/main.scss":"css/main.css"` (Dart Sass).
- To serve locally: `npx http-server -c-1` or `python -m http.server 8000`.

Edit notes

- SCSS source: `css/main.scss` (use root vars and `.search-bar`'s `--size`).
- Markup classes: `.search-bar`, `.search-bar__input`, `.search-bar__submit`.

Contributing

- Tiny demos: PRs welcome. Keep changes focused and dependency-free.

That's it.
