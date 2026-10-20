# Changelog

All notable changes to Echo are documented here.
The format follows [Keep a Changelog](https://keepachangelog.com/) and versions use [Semantic Versioning](https://semver.org/).

## [0.2.6] - 2026-10-20

### Added
- **In-app updates** — Echo now checks GitHub releases itself (Tauri updater, signed builds). When a new version exists a Liquid Glass dialog shows the release notes, downloads the installer with a live progress bar and installs on restart. Auto-check on startup (toggleable) plus a manual check, current version and last-check time in Settings › Motore.

## [0.2.5] - 2026-10-20

### Fixed
- **Active icons invisible in light mode** — the dark-mode fill override had higher CSS specificity than the ink rule, so fill-based glyphs (play/pause) stayed white on the crystal theme. Dark icon overrides are now scoped to `html:not(.light-mode)` and `currentColor` fills follow the element's colour: ink on glass, white on artwork.
- **Raw technical errors in toasts** — every remaining yt-dlp/Rust error shape (preview-gating, extractor crashes, age-gate, premiere, members-only, filesystem errors) maps to a friendly message; uncatalogued errors no longer leak raw text into the UI. Download, Mini Player and yt-dlp-update failures go through the same formatter.
- **Playback stuck on autoplay block** — a `NotAllowedError` used to leave the track buffering forever with no feedback; the footer now unsticks and the next user gesture resumes the track.
- **Error toasts readable** — they now stay visible ~5s instead of 2.5s.

## [0.2.4] - 2026-10-20

### Fixed
- **Disabled controls were invisible in light mode** — transport, footer, top bar and sidebar buttons now render as dimmed ink on the light glass instead of washing out to ghosts.

## [0.2.3] - 2026-10-20

### Added
- **True Liquid Glass shell** — panels, top bar, cards and menus are translucent lenses: `blur(30px) saturate(1.8)`, 1px specular inner borders and soft floating shadows instead of opaque surfaces and hard chrome.
- **Artwork ambient background** — the cover of the playing track becomes the blurred ambient backdrop of the whole app, crossfading on every track change.
- **Artists page** — a dedicated view with your personal ranking (listening time), followed artists, similar picks and the global chart. The sidebar ARTISTI section header is now a link to it.
- **Two-deck audio engine** — true crossfade and gapless transitions between tracks, with per-element HLS instances and a mid-track stall watchdog.
- **Floating dock footer** — the player bar is a detached island with a thinner seekbar, a finer handle and a longer volume bar.

### Changed
- **White icons, one accent** — every glyph is white; the only surviving accent is azzurro. Painted SVG strokes/fills are normalised, not just CSS colour.
- **Navigation** — Home lives in the top bar where genre browsing was; the sidebar Home row is now "Naviga per genere".
- **Sleep timer** removed from the footer.

### Fixed
- **Light-mode icons no longer disappear** — painted SVG strokes and fills flip to ink on the crystal theme; icons sitting on artwork stay white with a soft shadow.
- **Audio graph silence** — the bus reconnects during `ensureContext`, and a global pointerdown resumes the context for autoplay and deck transitions.
- **DJ remix transitions** — timing and track selection reworked on the two-deck engine.

## [0.2.2] - 2026-10-20

### Added
- **SoundCloud playlist importing** — paste a playlist URL or shortlink, Echo hydrates the metadata and creates native SoundCloud tracks (no wrong Deezer matches), reusing the SoundCloud playback path.
- First pass of the **Liquid Glass** restyle across sidebars, cards, menus, settings, lyrics/cinema mode and the player chrome.

## [0.2.1] - 2026-10-03

### Fixed
- **Artist pages were empty.** Deezer retired the chart/top endpoints the app used (`/artist/:id/top`, `/artist/:id/related`, `/artist/:id/radio`, `/chart/:id`), so popular tracks, "fans also like" and the artist radio never loaded.
- **The first-run artist picker had nothing to choose from** for the same reason — suggestions are back.
- **Home chart rows and the genre browser** were affected too; they are rebuilt from the same source.
- The app keeps the original endpoints as the primary path, so nothing changes if Deezer restores them.
-Added the ability to resize the left sidebar.

## [0.2.0] - 2026-10-03

### Added
- **Profile dashboard** — top artists, top tracks, daily listening chart, distribution breakdown and a summary card.
- **Next-track preview** — the upcoming song peeks beside the cover in the lyrics view.
- **Theme presets** and a custom accent colour that now reaches every control.
- **Clipping protection** — per-track level analysis with a measured peak ceiling, next to loudness normalisation.
- **Mini player** — volume control, mute toggle and app-styled tooltips.
- **Pixel wordmark** in the titlebar.

### Changed
- **Redesigned panels, cards and controls** across the app: defined edges, layered depth, consistent hover and press states.
- **Lyrics** — the current-line card wraps long lines instead of cutting them with an ellipsis.
- **Mini player** rebuilt on the app's design tokens: it follows light/dark mode, theme presets and the accent colour.
- **Settings** — segmented pickers, switches and action buttons unified (heights, radii, focus rings).
- **Skipping a track** in the lyrics view slides smoothly instead of cutting.
- Smoother theme switching (wave transition) and `prefers-reduced-motion` support in more places.

### Fixed
- Loudness normalisation no longer silences tracks (the previous audio graph could mute streams it couldn't read).
- Clipping protection now measures the track instead of guessing from the volume slider.
- Alignment, focus-ring and light-mode issues across settings, profile and the mini player.

### Known issues
- **Echo AI is temporarily paused** in this build while the local model backend is reworked.

## [0.1.0] - 2026-XX-XX

First public release.

### Added
- Multi-source streaming playback
- Library: playlists, favourites, listening history and statistics
- Synced lyrics with manual sync offset
- Echo AI assistant (local models) with chat, agent and voice modes
- DJ view and mix library
- Mini player, picture-in-picture and system tray
- Discord Rich Presence
- Light/dark mode and a custom theme editor
- Full localisation: English, Italiano, Español, Français, Deutsch, Português
- Downloads, sleep timer, crossfade, volume normalisation
