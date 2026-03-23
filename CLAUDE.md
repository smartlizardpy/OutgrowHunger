# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Outgrow Hunger** is a browser-based educational game about hunger, resilience, and community trust, built for Games for Change. It's a 30-day survival/resource-management game set in a fictional drought-stricken community (San Isidro Ward).

## Architecture

The entire game lives in a **single monolithic HTML file** (`game.html`) with embedded CSS and JavaScript — no frameworks, no build step, no dependencies. This is intentional for easy distribution (e.g., uploading to Itch.io as a zip).

### Key sections within `game.html`:
- **CSS** (top ~860 lines): Responsive layout with CSS variables for theming. Breakpoints at 480px (mobile), 900px (tablet), 980px (desktop grid).
- **HTML** (middle): Screen-based UI — start screen → character select → main game → end screen, plus modal overlays for minigames and help.
- **JavaScript** (line ~1050 onward): All game logic including event system, stat management, minigames, audio, and day advancement.

### Core game systems:
- **Events**: 15 randomized daily events (`eventsData` array), each with category, 4+ choices, stat effects, optional trait requirements, and optional minigame triggers.
- **Stats**: Hunger, Resilience, Community Trust (percentages) + Food, Water, Money, Knowledge (integers).
- **Characters**: 4 playable characters (Maya/Teacher, Liam/Farmer, Sam/Merchant, Elena/Doctor), each with a trait that modifies gameplay mechanics.
- **Difficulty**: Easy/Normal/Hard — affects resource modifiers, hunger rate, and trust decay rate.
- **Trust momentum**: Streak bonuses at high trust, emergency rescue mechanic at low trust.
- **Minigames**: 7 types (reflex, sequence, plant, guess, memory, rapid-tap, planning) triggered by specific event choices.
- **Nightly cycle**: Hunger increases, trust decays, conditional resilience penalties, chance of community support. Final night (day 30) skips hunger increase to prevent unwinnable end states.

### Other pages:
- `index.html` — redirects to `game.html`
- `tutorial/index.html` — interactive tutorial with live stat simulation
- `about-us/index.html` — team credits page

## Running Locally

```bash
python3 -m http.server 8000
# Visit http://localhost:8000/game.html
```

Or open `game.html` directly in a browser. No build or install step required.

## Development Notes

- **No build tools, package manager, or test framework** — all changes are direct edits to HTML/CSS/JS files.
- **Debug mode**: Set `DEBUG_BALANCE = true` in the JS section to enable balance testing output.
- **Audio**: Procedurally generated via Web Audio API (no audio files).
- **Assets**: Character avatars in `assets/` (AI-generated PNGs).
- **Color palette**: Primary `#4a7c59` (earthy green), secondary `#8cba80`, accent `#e6b89c`, danger `#d9534f`, warning `#f0ad4e`.

## Win/Lose Conditions

- **Win**: Reach day 30 with Hunger < 10% AND Resilience > 80%
- **Lose**: Hunger ≥ 100%, Resilience ≤ 0%, or Trust ≤ 0%

## Git Workflow

- `master` is the main/release branch
- `dev` is the active development branch
