# Changelog

## [2.0.9] - 2026-09-01

### Changed
- Security & stability improvements

## [2.0.8] - 2026-07-17

### Added
- Video (MP4) and animated GIF backgrounds — pick from gallery or load via URL
- Video sound toggle (mute/unmute)
- Blur slider: set blur to 0 for a fully clear see-through card, or up to 28 for heavy frosted glass
- 8 new themes: Tokyo Night, Dracula, Synthwave, Amber, Forest, Cobalt, Sunset, Ice


## [2.0.7] - 2026-07-07

### Added
- Rich ban card with colored badges for ban type, violation, appeal availability
- Appeal status banner: Under Review / Unbanned / Rejected / No Appeal Filed
- Timestamps for ban date and appeal filing date
- EU account indicator
- 9 themes: Ghost, Neon Purple, Crimson, Cyber, Sakura, Void (+ Ocean Blue, Matrix, Rose Gold)

### Changed
- Ghost UI: transparent cards, hairline borders, near-zero color
- Settings dialog redesigned with glassmorphism to match app aesthetic
- Result dialog adapts to selected theme colors
- Status banner glow and color intensity reduced
- Ban card labels in English
- Batch mode removed

### Fixed
- Violation labels and ban type classification

## [2.0.6] - 2026-05-21

### Added
- Glassmorphism card design — card blurs background image for frosted glass effect
- Transparency slider (0–100%) for card opacity and background overlay darkening
- Theme presets: Neon Purple, Ocean Blue, Matrix, Rose Gold — one tap to switch
- Number history: last 30 checked numbers with status badge and timestamp, stored encrypted
- Batch check mode: enter multiple numbers (one per line) and check all at once
- Copy button directly on the status result banner
- Hex color input (`RRGGBB`) in settings color picker — pick any color
- Settings dialog reorganized into collapsible sections (Themes, General, Transparency, Colors, Texts, Result dialog, Background)

### Changed
- Result dialog redesigned: wider layout, dark glass background, colored left status bar, all-white text
- Status, details and batch result panels now use glassmorphism (blur + transparent background)
- All transparency elements scale correctly with card opacity — truly invisible at 0%
- Full English UI — all labels, section titles and messages translated
- targetSdk bumped to 37, minSdk lowered to 21
- ProGuard rules strengthened: 7 optimization passes, tighter keeps, Kotlin null-check removal

### Fixed
- Card not going fully transparent at 0% opacity (gradient replaced with direct alpha color)
- Inner card border and shadow now fade with opacity instead of staying hardcoded visible
- Result dialog background was using accent color as solid fill — now always dark glass

## [2.0.5] - 2026-04-18

### Added
- In-app APK download & install with live progress bar — fallback to browser if permission denied
- Share BanChecker button in menu
- Telegram channel & website links in menu

### Security
- APK signature check, DEX integrity check, clone/repackage protection
- Encrypted local storage (AES)

### Fixed
- Black screen on startup on some devices

## [2.0.4] - 2026-04-11

### Changed
- Update now opens directly in browser instead of in-app download
- Removed `REQUEST_INSTALL_PACKAGES` permission for Play Store compliance

## [2.0.3] - 2026-04-11

### Fixed
- "Open in Browser" and "Install Now" buttons in the update dialog now work correctly
- "Open in Browser" opens the GitHub releases page instead of doing nothing
- Added missing Android manifest queries for `https://` — `canLaunchUrl` returned false on Android 11+ without it
- Null-safe URL handling to prevent crashes when `apkUrl` is missing

### Added
- In-app APK download dialog with real progress bar (MB downloaded + percentage)
- Automatic installer launch after download completes

## [2.0.2] - 2026-04-11

### Security
- Obscured the API
- Added User-Agent validation — only official app requests are accepted

## [2.0.1] - 2026-04-04
### Fixed
- Non-`temporarily_unavailable` API fail responses are now treated as unbanned results
- `temporarily_unavailable` responses still show as a temporary service warning
- Cleaned update-service logging behavior in the app

### Changed
- Bumped the app version to `2.0.1`

## [2.0.0] - 2026-04-04
### Added
- Flutter-native app interface replacing the previous HTML/WebView-based runtime
- Optional result dialog with separate settings for dialog colors and texts
- Crash reporting with file logging and a visible crash popup
- Four APK variants for easier installation across different Android device architectures

### Changed
- Updated the app package to the `2.0.0` release line
- Improved the result dialog design with a darker semi-transparent background and simplified styling

### Fixed
- Fixed ban-check handling for temporary  availability problems so they no longer appear as normal unbanned results
- Fixed background image handling for base64 data sources

### Performance
- Reduced app size to under 43 MB
- Reduced lag by removing the old embedded web runtime and moving to a Flutter-native interface
- Improved startup and overall stability

## [1.0.0] - 2026-01-24
### Added
- Initial release
- Core banned number checker functionality
- Support for multiple number lists
- In-app update system
- GitHub Releases integration
- Direct APK download

### Technical
- Flutter 3.x
- Dart null safety
- HTTP caching with ETag support
- SHA-256 integrity verification
