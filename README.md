# Outgrow Hunger

Outgrow Hunger is a browser-based serious game about hunger, resilience, and community trust.
Players make day-to-day survival decisions, manage limited resources, and face social trade-offs that mirror real-world food insecurity pressures.

## What the Game Covers

- Hunger and health pressure over 30 in-game days
- Resource management: Food, Water, Dollars, Knowledge
- Community trust as a social survival mechanic
- Character traits with different strategic advantages
- Event-driven choices with consequences
- Mini-challenges for high-impact decisions

## Core Loop

1. Choose a character
2. Receive a daily event
3. Make a choice (sometimes with a mini-challenge)
4. Manage resources and stats
5. End the day and face nightly decay/bonuses
6. Survive to Day 30 with required thresholds

## Win / Lose Conditions

### Win (Day 30 check)
- Hunger below 10%
- Resilience above 80%

### Instant lose
- Hunger reaches 100%
- Resilience reaches 0%
- Trust reaches 0%

## Controls

- Mouse / touch input only
- Click/tap choice buttons to play

## Project Structure

- `game.html` - Main game (UI, styling, and logic in one file)
- `about-us/index.html` - About page + team section
- `assets/images/` - Image assets placeholder
- `assets/audio/` - Audio assets placeholder
- `docs/release-checklist.md` - Packaging and release checklist
- `feedback.txt` - Teacher feedback notes

## Run Locally

Because this is static HTML/CSS/JS, you can run it in several ways:

1. Open `game.html` directly in a browser.
2. Or run a local static server from repo root (recommended):

```bash
python3 -m http.server 8000
```

Then open:

- `http://localhost:8000/game.html`
- `http://localhost:8000/about-us/`

## Design / Dev Notes

- The gameplay currently favors rapid iteration in a single-file architecture.
- Internal stat key for dollars is `money` (UI label is `Dollars`).
- Mini-game difficulty scales with day progression.
- Trust system includes decay and high-trust support moments.

## Publishing (Itch.io)

Use `docs/release-checklist.md` for final release steps.
Recommended flow:

1. Zip project root preserving folder structure.
2. Upload as HTML game on itch.io.
3. Set launch file to `game.html`.
4. Smoke-test laptop + mobile viewports.

## Credits

- Ateş Demir
- Ozan Kaygusuz
- Sohan

