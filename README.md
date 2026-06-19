# aegis-sankhacooray-com

Public landing + wrapper for **Aegis**, served at
**https://aegis.sankhacooray.com** via GitHub Pages.

This repo is intentionally thin: a single `index.html` that brands Aegis and
launches / embeds the login-gated Apps Script web app
([`aegis-sankhacooray-appscript`](https://github.com/sankhacooray/aegis-sankhacooray-appscript)).

## How it works

- The app's `/exec` URL is injected into `index.html` in place of the
  `__AEGIS_APP_URL__` placeholder (see the deploy wiring step).
- "Sign in with Google" embeds the app in an iframe. Google's consent screen
  cannot render inside a frame, so first-time / unauthorized users use the
  **Open in new tab ↗** link, which launches the app top-level.

## Hosting

- **GitHub Pages** from the `main` branch root.
- Custom domain pinned by the `CNAME` file (`aegis.sankhacooray.com`).
- DNS: a Cloudflare `CNAME aegis → sankhacooray.github.io`.
- `.nojekyll` disables Jekyll processing.

## Updating the app URL

Replace `__AEGIS_APP_URL__` in `index.html` with the current Apps Script
deployment `/exec` URL and push to `main`.
