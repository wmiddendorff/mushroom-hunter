# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Project Overview

Mushroom Hunter is a single-file educational web game about Michigan mushroom identification. It teaches players to distinguish between edible, poisonous, deadly, and medicinal-only mushrooms.

**Status:** MVP complete, playable
**Tech:** Pure HTML/CSS/JS, no build step

## Architecture

Everything is in `index.html`:
- CSS styles (dark forest theme with gradients)
- JavaScript game logic
- Mushroom database (16 species)

### Mushroom Data Structure

```javascript
{
    name: "Morel",
    scientific: "Morchella esculenta",
    emoji: "🍄",
    appearance: "Description of visual features",
    habitat: "Where and when to find it",
    answer: "edible" | "poisonous" | "deadly" | "medicinal",
    funFact: "Educational content shown after answer",
    difficulty: 1 | 2  // 1=easy, 2=hard
}
```

### Game Flow

```
Start Screen → Select Difficulty → Question Loop → Results
                                        ↓
                              Show answer + fun fact
                                        ↓
                                  Next question
```

## Adding New Mushrooms

Add to the `mushrooms` array in index.html:

```javascript
{
    name: "Species Name",
    scientific: "Latin name",
    emoji: "🍄",
    appearance: "Visual description for identification",
    habitat: "Location, substrate, season",
    answer: "edible",  // or poisonous, deadly, medicinal
    funFact: "Educational fact shown after answering",
    difficulty: 1  // 1=easy (obvious), 2=hard (lookalikes)
}
```

## Styling Conventions

- Dark theme with forest-inspired gradients
- Primary accent: `#76b852` (mushroom green)
- Card backgrounds: `rgba(255,255,255,0.08)`
- Border radius: 12px for cards, 30px for buttons
- Animations: `float` for mushroom, `pulse-green` for correct, `shake` for wrong

## Future Enhancements

1. **Add real photos** - Replace emoji with public domain mushroom photos
2. **More species** - Expand beyond 16 Michigan mushrooms
3. **Seasonal mode** - Only show mushrooms currently in season
4. **Location variants** - Different regions have different species
5. **Expert mode** - Identify from partial information

## Safety Note

The game emphasizes safety:
- Warning box on start screen
- "When in doubt, throw it out" messaging
- Clear distinction between poisonous vs deadly
- Fun facts include safety information

## Running Locally

```bash
# Just open in browser
open index.html

# Or serve with any HTTP server
python -m http.server 8080
npx serve .
```

## Files

| File | Purpose |
|------|---------|
| `index.html` | Complete game (HTML + CSS + JS) |
| `README.md` | Project documentation |
| `CLAUDE.md` | Claude Code guidance |
