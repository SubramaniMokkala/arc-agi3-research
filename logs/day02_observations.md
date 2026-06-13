# ARC-AGI-3 Research — Observations Log

## Day 02 — LS20 Environment First Contact (June 12, 2026)

### What I can see in the game
- The environment is a 64x64 grid encoded as integer color values
- There is a cyan square that moves — this is the player
- There is a blue/orange object that does not move — likely a static collectible
- There is a red structure forming walls and corridors
- The top center has a symbol in a box — likely the level goal/exit
- Bottom left shows a minimap or level indicator
- Bottom bar is a resource bar that depletes over time/actions

### Hypothesis about the goal
- Player must navigate to the top exit symbol
- Collecting the blue/orange object may grant bonus moves
- GAME_OVER triggered when the resource bar fully depletes

### Action mapping (verified June 13)
- ACTION1 = up
- ACTION2 = down
- ACTION3 = left
- ACTION4 = right

### New observations (June 13)
- Progress bar decremented after ACTION1 but not others — may relate to wall collision
- ACTION4 moved player 2 steps instead of 1 — possible momentum or speed difference
- Blue/orange object did not move in any frame — static collectible confirmed

### Testable Hypotheses
1. Bottom bar = moves remaining. Test: count exact steps to GAME_OVER across multiple runs.
2. Cyan collectible grants bonus moves when collected. Test: compare runs with and without collecting.
3. ACTION4 has different speed/momentum. Test: take ACTION4 multiple times and track distance moved.

### Questions still open
- What exactly triggers the bar to decrement — every action or only wall hits?
- Does the exit require the collectible first or can player go directly?
- Are all 7 levels variations of the same layout or completely different?