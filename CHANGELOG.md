# Changelog

All notable changes to Echo are documented here.
The format follows [Keep a Changelog](https://keepachangelog.com/) and versions use [Semantic Versioning](https://semver.org/).

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
