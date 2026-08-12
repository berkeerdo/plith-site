# plith.app — landing site

Marketing site for [Plith](https://github.com/berkeerdo/Plith), a modern
Windows audio OSD. Lives at **https://plith.app**.

## Stack

- **Astro 7** — static site generation.
- **Tailwind CSS 4** (via `@tailwindcss/vite`) — styling.
- **@astrojs/sitemap** — auto-generates `sitemap-index.xml`.
- Vanilla TypeScript for the interactive OSD demo + Settings simulator.

## Content

- **Hero** — pitch, download CTA, "Windows Desktop · Live demo" mock with
  a fully interactive recreation of Plith's OSD (arrow keys change volume,
  space toggles play/pause, ←/→ skips tracks).
- **Features** — six-card grid: Voicemeeter-first, Windows Core Audio
  fallback, endpoint pinning, SMTC media, Game mode, summon hotkey.
- **Settings simulator** — faithful browser reproduction of Plith's real
  Settings window, mirrored from `SettingsWindow.xaml`. Every knob updates
  a live OSD preview on the right in real time.
- **Download** — links to the latest GitHub release.
- **FAQ** — SmartScreen, Voicemeeter, Game mode, endpoint pinning,
  MSIX/Store status.

Both OSD and Settings mirror the real Plith palette and dimensions
(`#4AD695` accent, `Palette.Dark.xaml` / `OsdPalette.Dark.xaml`).

## Local development

```powershell
npm install
npm run dev          # http://127.0.0.1:4321
npm run build        # → dist/
npm run preview      # serve dist/ locally
```

## Deployment

`npm run build` emits a purely static `dist/` — no runtime, no server
component. Deployed behind Cloudflare (proxy + Full-strict SSL) with a
long-cache header on the hashed `_astro/` bundle.

## License

Site source: MIT. Plith itself is also MIT — see the
[main repo](https://github.com/berkeerdo/Plith/blob/main/LICENSE).
