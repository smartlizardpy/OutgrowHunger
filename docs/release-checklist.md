# Outgrow Hunger Release Checklist

## Build Packaging
- Keep gameplay entry point at `game.html`.
- Keep About page at `about-us/index.html`.
- Bundle all media under:
  - `assets/images/`
  - `assets/audio/`

## Itch.io Upload Steps
1. Zip the project preserving folders.
2. On itch.io create a new HTML game project.
3. Upload the zip and set launch file to `game.html`.
4. Enable fullscreen + mobile friendly options.
5. Add short description, controls, and credits.

## QA Smoke Test
- Laptop viewport (1366x768): no blocking overflow in game screen.
- Mobile viewport (390x844): screens remain playable.
- About page route works at `/about-us/`.
- Core loops verified:
  - resource spend/recovery
  - trust gain/loss + support events
  - mini-games scale with day progression

## Credits
- Ateş Demir
- Ozan Kaygusuz
- Sohan
