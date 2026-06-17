# Alien.exe
 
A classic arcade-style space shooter built with Python and Pygame. Control your ship, destroy waves of alien fleets, survive as long as possible, and climb the high score leaderboard — all getting progressively harder with each level.
 
---
 
## Gameplay
 
- Move your ship left and right using the **arrow keys**
- Fire bullets with the **spacebar**
- Destroy the entire alien fleet to advance to the next level
- Each new level moves faster and is worth more points
- You have **3 ships** — lose them all and the game ends
- Press **Q** to quit at any time
 
---
 
## Features
 
- Smooth, continuous ship movement with boundary limits
- Alien fleet that moves sideways and drops down as it reaches screen edges
- Collision detection for bullets vs aliens and aliens vs ship
- Progressive difficulty — speed increases with each level cleared
- Live scoring with comma-formatted numbers, rounded to the nearest 10
- Persistent high score tracking per session
- Level counter displayed below your score
- Remaining ships shown graphically in the top-left corner
- Play button to start or restart the game
- Mouse cursor hidden during active gameplay
 
---
 
## Tech Stack
 
- **Language:** Python 3
- **Library:** Pygame
- **Architecture:** Multi-file OOP with a dedicated settings, stats, and game functions module
 
--- 
## Getting Started
 
### 1. Clone the repository
 
```bash
git clone https://github.com/anasahhm/orbital-warzone.git
cd orbital-warzone
```
 
### 2. Install Pygame
 
```bash
pip install pygame
```
 
> If you're using Python 3 and `pip` points to Python 2, use `pip3` instead.
 
### 3. Run the game
 
```bash
python alien_invasion.py
```
 
---
 
## Settings
 
All game settings live in `settings.py`. Tweak these to adjust difficulty:
 
| Setting | Default | Description |
|---|---|---|
| `screen_width` | 1200 | Game window width in pixels |
| `screen_height` | 800 | Game window height in pixels |
| `ship_speed_factor` | 1.5 | Ship movement speed |
| `ship_limit` | 3 | Number of lives |
| `bullet_speed_factor` | 3 | Bullet travel speed |
| `bullet_width` | 3 | Bullet width in pixels |
| `bullets_allowed` | 3 | Max bullets on screen at once |
| `alien_speed_factor` | 1 | Alien movement speed |
| `fleet_drop_speed` | 10 | How far fleet drops per direction change |
| `speedup_scale` | 1.1 | Speed multiplier per level |
| `score_scale` | 1.5 | Point value multiplier per level |
| `alien_points` | 50 | Starting points per alien kill |
 
---
## Key Classes
 
### `Ship`
Handles player movement, boundary checking, and rendering. Stores `moving_right` and `moving_left` flags for smooth continuous motion.
 
### `Alien`
Represents a single alien. Checks screen edges and moves in the direction set by `fleet_direction` in settings.
 
### `Bullet`
A sprite-based rectangle that travels up the screen. Removed automatically when it passes the top edge.
 
### `GameStats`
Tracks `ships_left`, `score`, `high_score`, `level`, and `game_active` state. Most stats reset on new game; high score persists for the session.
 
### `Scoreboard`
Renders score, high score, level, and remaining ships as graphical elements drawn to the screen each frame.
 
### `Button`
A reusable filled rectangle with a centered text label. Used for the Play button; easy to extend for other UI elements.
 
---
 
## Controls
 
| Key | Action |
|---|---|
| `←` / `→` Arrow Keys | Move ship left / right |
| `Spacebar` | Fire bullet |
| `Q` | Quit game |
| Mouse click on Play | Start / restart game |
 
---
