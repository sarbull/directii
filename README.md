# directii landing page

The page that presents directii: what it does, on the web and on Android, with a way into the web app (the `aplicatia` project, on **aplicatia.directii.ro**). It's one static page, `index.html`, with its styles and its small script inline: no build, no dependencies.

- **Romanian by default, English on request,** like the app: the RO / EN switch in the header, remembered in the browser.
- **Light or dark,** following the system, in the app's colors (`aplicatia/src/css/style.css`).
- **The phone and car screens are drawn, not screenshots:** HTML and inline SVG with the app's own tokens, report kinds and colors (`aplicatia/src/js/report-types.js`) and wording (`aplicatia/src/js/locales/`), so they follow the theme and the language. When the app's look or words change, change them here too.

## Run

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8080    # http://localhost:8080
```

## Deploy

Not set up yet. It's static files, so it can go the way `aplicatia` does: nginx on Dokku, as in `../deploy/aplicatia`.

## How it's laid out

```
index.html     the page: styles in <head>, Romanian in the markup, English in EN at the bottom
icon.svg       the app's icon (a copy of aplicatia/public/icon.svg)
icon.png       the same, for apple-touch-icon (a copy of aplicatia/public/icon.png)
```

**Changing text:** the Romanian is in the markup. An element with `data-i18n="key"` gets `EN[key]` in English, and one with `data-i18n-label="key"` gets it as its `aria-label`. Change both languages together.
