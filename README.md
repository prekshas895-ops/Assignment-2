 # Console Dodger Game - Modifications Log

This section documents the enhancements implemented to the core game logic.

## Implemented Modifications

We selected two features that satisfy the modification requirements (one High-Level feature and one Simple feature).

### 1. Simple Feature: Difficulty Levels (Based on Score)

The game's speed now progressively increases as the player successfully dodges obstacles, providing a greater challenge over time.

* **Scoring Logic:** A global `score` variable is initialized to 0. It increments by **1** every time an obstacle successfully passes the player's position (`step == 10` and `x != obstaclePos`).
* **Difficulty Scaling:** The game speed is controlled by the `gameSpeed` variable (initial value: `120ms`).
    * For every **5 points** scored, `gameSpeed` is reduced by **10ms**, making the delay shorter and the obstacle movement faster.
    * A minimum speed limit (`50ms`) is enforced to keep the game playable.
* **Display:** The current score is printed at the top of the console during gameplay, and the final score is displayed on the "GAME OVER" screen.

### 2. High-Level Feature: Sound Effects & Background Audio (Refinement)

The audio handling was refined for a better user experience.

* **Background Music (`bg.wav`):** Uses the `SND_LOOP` flag to ensure the background music plays continuously until the game ends.
* **Impact Sound (`impact.wav`):** The background music is explicitly stopped (`PlaySound(NULL, NULL, 0)`) immediately upon collision before the impact sound is played, preventing audio overlap.


