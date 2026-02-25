# Outgrow Hunger

A browser-based survival strategy game built in a single HTML file.

## Overview

**Outgrow Hunger** is a day-by-day decision game where you manage:
- Hunger
- Resilience
- Community Trust
- Resources (Food, Water, Money, Knowledge)

You choose a character with a unique trait, react to random events, and try to survive and thrive through Day 30.

## Run the Game

No build step is required.

1. Open `game.html` in any modern browser.
2. Click **Start New Game**.

Optional (local server):

```bash
python3 -m http.server
```

Then visit `http://localhost:8000`.

## How to Play

1. Choose a difficulty: `Easy`, `Normal`, or `Hard`.
2. Pick a character (each has different starting bonuses and a special trait).
3. For each day:
- Read the random event.
- Pick one event choice.
- Use action buttons if needed (`Eat`, `Drink`).
- End the day.

Event choice buttons show a preview of stat/resource deltas before you click.

## Win and Lose Conditions

### Win
On Day 30, finish with:
- `Hunger < 10%`
- `Resilience > 80%`

### Immediate Loss
You lose instantly if any of these occur:
- `Hunger >= 100%`
- `Resilience <= 0%`
- `Trust <= 0%`

## Features

- Character selection with trait-gated options
- Difficulty modifiers
- Randomized event system
- Progress bars and live stat UI
- Resource action bar
- Floating combat-style feedback text
- Sound effects via Web Audio API
- End screen summary and restart/menu flow

## File Structure

- `game.html` - Full game (HTML, CSS, JS)
- `README.MD` - Project documentation

## Notes

This project is intentionally lightweight and self-contained for easy sharing and quick iteration.
