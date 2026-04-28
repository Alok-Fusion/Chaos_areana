# Velocity Dash 3D - Game Specification

## Project Overview
- **Project Name**: Velocity Dash 3D
- **Type**: 3D Endless Runner Web Game
- **Core Functionality**: Premium 3-lane endless runner with Three.js 3D graphics, anti-boredom events, multiple maps, and deep progression
- **Target Users**: Casual gamers seeking highly addictive, stimulating gameplay

---

## Technical Specification

### Tech Stack
- **Three.js** (via CDN: https://unpkg.com/three@0.160.0/build/three.module.js)
- Single HTML file with embedded JavaScript modules
- Web Audio API for synthesized sounds
- LocalStorage for persistence
- Responsive design for desktop + mobile

### Game Dimensions
- Full browser viewport
- 3 lanes with smooth interpolation
- 60 FPS target

---

## Visual Design Specification

### Color Palettes by Theme

**Desert Highway**:
- Sky: #ff8844 → #ffcc88 (sunset gradient)
- Ground: #c49a6c
- Road: #4a4a4a
- Accent: #ff6600 (orange neon)

**Cyber City**:
- Sky: #0a0a20 → #1a0a3a (dark purple)
- Ground: #151525
- Road: #2a2a3a
- Accent: #00ffff (cyan neon)
- Neon signs: #ff00ff (magenta)

**Snow Mountain**:
- Sky: #aaccee → #4488aa (cold blue)
- Ground: #e8f0ff
- Road: #556677
- Accent: #44aaff (ice blue)

**Space Highway**:
- Sky: #000011 → #000033 (deep space)
- Stars: #ffffff
- Road: #1a1a2a
- Accent: #aa44ff (purple nebula)

### Typography
- Primary Font: 'Orbitron' (Google Fonts)
- Secondary Font: 'Exo 2' (Google Fonts)
- HUD: 24px Orbitron
- Menus: 36px title, 16px body

### Visual Effects
- Fog for depth
- Dynamic shadows
- Particle systems (dust, coins, sparks)
- Screen shake on collision
- Speed lines
- Chromatic aberration at high speed
- Bloom effect on neon objects

---

## UI/UX Specification

### Screens
1. **Loading** - Animated progress bar
2. **Main Menu** - Logo, Play button, mode select
3. **Character Select** - 3D preview cards
4. **Shop** - Grid of unlockables
5. **Settings** - Audio, controls info
6. **HUD** - Score, coins, lives, powerups, combo
7. **Game Over** - Stats, rewards
8. **Event Popup** - Surprising events

### Controls
- **Desktop**: Arrow keys / WASD / Space
- **Mobile**: Swipe gestures
- **Pause**: ESC / P / double-tap

---

## Gameplay Specification

### Core Mechanics
- Player auto-runs on endless road
- 3 lanes: -1 (left), 0 (center), +1 (right)
- Jump: 0.6s duration, invincibility frames
- Slide: 0.5s duration, smaller hitbox
- Lane switch: 0.15s smooth lerp

### Obstacles
1. **Truck** - Large, block entire lane
2. **Barrier** - Low, jump over
3. **Cone** - Jump over
4. **Pit** - Jump across
5. **Laser** - Slide under
6. **Moving Car** - Dodge

### Collectibles
- **Coin** - +10 points, golden
- **Gem** - +50 points, rare
- **Mystery Box** - Random effect

### Scoring
- Distance: 1 point per meter
- Combo: 2x-5x multiplier
- Coins: 10 points
- Gems: 50 points

### Progression
- Speed: Starts 20m/s, +1m/s per 100m
- Max speed: 50m/s

---

## Anti-Boredom Events

Trigger every 20-40 seconds randomly:

1. **Giant Chicken** - Walks across road
2. **UFO Abduction** - Lifts random obstacle away
3. **Low Gravity** - Bouncy mode for 10s
4. **Reverse Controls** - Backward challenge
5. **Coin Rain** - Coins fall from sky
6. **Slow Motion** - Cinematic chase
7. **Boss Truck** - Giant enemy appears
8. **Dance Party** - Neon lights, music change
9. **Earthquake** - Road shakes violently
10. **Portal** - Warps to new map section
11. **Boulder Chase** - Giant boulder rolls behind
12. **Meteor Shower** - Dodging meteors
13. **Shortcut Choice** - Risk/reward paths
14. **Treasure Vault** - Bonus round
15. **Turbo Tunnel** - High speed section

---

## Game Modes

1. **Endless** - Standard infinite run
2. **Time Attack** - Reach distance in time
3. **Coin Rush** - Maximize coins
4. **One Life** - No respawns
5. **Daily Challenge** - Special objectives

---

## Maps/Themes

1. Desert Highway
2. Cyber City
3. Snow Mountain
4. Space Highway
5. Lava World (future expansion)

---

## Characters

1. **Runner** - Default, balanced
2. **Ninja** - Faster, costs 500
3. **Robot** - Tanky, costs 1000
4. **Panda** - Lucky, costs 750
5. **Alien** - Unique abilities, costs 1500
6. **Secret** - Unlock via achievement

---

## Powerups

1. **Shield** - One-hit protection (10s)
2. **Magnet** - Attracts coins (8s)
3. **2x Coins** - Double value (12s)
4. **Slow Mo** - 50% speed (6s)
5. **Invincible** - Full run god mode (5s)

---

## Audio

- Synthesized via Web Audio API
- Jump whoosh
- Slide swoosh
- Coin chime
- Crash impact
- Event fanfare
- Menu clicks
- Background beats (toggleable)

---

## Data Persistence

LocalStorage keys:
- `vd3d_coins` - Currency
- `vd3d_gems` - Premium currency
- `vd3d_highscore` - Best score
- `vd3d_characters` - Unlocked chars
- `vd3d_themes` - Unlocked themes
- `vd3d_settings` - Audio settings
- `vd3d_daily` - Last daily reward

---

## Acceptance Criteria

1. Game loads and displays menu
2. 3D road renders with perspective
3. Player moves between 3 lanes
4. Jump and slide work
5. Obstacles spawn and are avoidable
6. Coins are collectible
7. Score increments from distance
8. Speed increases over time
9. Collision ends game/loses life
10. Anti-boredom events trigger
11. Multiple themes work
12. Characters are selectable
13. Shop allows purchases
14. Audio plays with toggle
15. Data saves to localStorage

---

## File Structure

Single file: `index.html` (self-contained Three.js game)