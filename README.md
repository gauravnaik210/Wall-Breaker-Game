# Break All Walls - Breakout Game

A classic Breakout/Brick Breaker game inspired by the original Atari 1976 arcade game, built with LÖVE 2D (Love2D) game engine. This version features a 16:9 widescreen presentation with modern pixel-perfect rendering.

## Overview

Break All Walls is a single-player brick-breaking game where the player controls a paddle at the bottom of the screen to deflect a ball upward, destroying bricks arranged at the top. The game features multiple paddle skins, progressive difficulty levels, scoring system, and high score tracking.

## Features

- **Multiple Paddle Skins**: Choose from 4 different colored paddle designs
- **Progressive Levels**: Randomly generated brick layouts with increasing difficulty
- **Brick System**: Bricks have multiple tiers with different colors and point values
- **Physics**: Realistic ball physics with angle-based paddle collision detection
- **Health System**: Player starts with 3 lives; lose health when the ball falls below the paddle
- **Score Tracking**: Accumulate points by destroying bricks; collect high scores
- **High Score Leaderboard**: Top 10 scores with player names stored persistently
- **Audio**: Sound effects for paddle hits, brick breaks, scoring, and background music
- **State Management**: Smooth transitions between game states (start, paddle select, serve, play, victory, game over, high scores)

## Project Structure

```
Break All Walls/
├── main.lua                 # Entry point and main game loop
├── fonts/                   # Game fonts
├── graphics/                # Sprite sheets and images
├── sounds/                  # Audio files (SFX and music)
├── lib/                     # Third-party libraries
│   ├── class.lua           # OOP class system (HUMP)
│   └── push.lua            # Virtual resolution management
└── src/                     # Game source code
    ├── Dependencies.lua    # Module imports and initialization
    ├── constants.lua       # Game configuration constants
    ├── Ball.lua           # Ball physics and collision
    ├── Brick.lua          # Brick class with particles
    ├── Paddle.lua         # Paddle movement and rendering
    ├── LevelMaker.lua     # Level generation algorithm
    ├── StateMachine.lua   # Game state management
    ├── Util.lua           # Utility functions for sprite sheets
    └── states/            # Individual game states
        ├── BaseState.lua
        ├── StartState.lua
        ├── PaddleSelectState.lua
        ├── ServeState.lua
        ├── PlayState.lua
        ├── VictoryState.lua
        ├── GameOverState.lua
        ├── HighScoreState.lua
        └── EnterHighScoreState.lua
```

## Game States

1. **Start Screen**: Main menu with options to start or view high scores
2. **Paddle Selection**: Choose your paddle skin (4 options)
3. **Serve**: Ready screen with the paddle and ball, press Enter to begin
4. **Play**: Main gameplay where you break bricks and earn points
5. **Victory**: Level completion screen, shows next level and score
6. **Game Over**: Final score display, check if it qualifies for high scores
7. **Enter High Score**: Arcade-style name entry for new high scores (3 characters)
8. **High Scores**: Display top 10 scores leaderboard

## How to Play

1. Run the game with LÖVE 2D: `love .`
2. Navigate the menu with UP/DOWN arrows
3. Select "START" and choose your paddle skin
4. Press ENTER to serve the ball
5. Use LEFT/RIGHT arrow keys to move the paddle
6. Destroy all bricks to advance to the next level
7. Press SPACE to pause/resume during gameplay
8. Press ESC to quit at any time

## Scoring System

- **Brick Points**: Color × 25 + Tier × 200
  - Colors: 1-5 (higher = more points)
  - Tiers: 0-3 (higher = more points)
- **Health Recovery**: Earn extra health for reaching score milestones
- **High Score Milestone**: Recover points double each time you gain health

## Technical Details

- **Engine**: LÖVE 2D (Love2D)
- **Language**: Lua
- **Virtual Resolution**: 432×243 (upscaled to 1280×720 default window)
- **Rendering**: Pixel-perfect with nearest-neighbor filtering
- **Display**: Widescreen (16:9) format

## Controls

| Key | Action |
|-----|--------|
| UP/DOWN | Navigate menus |
| LEFT/RIGHT | Move paddle / Select paddle |
| ENTER | Confirm selection / Serve ball |
| SPACE | Pause / Resume (during play) |
| ESC | Quit game |

## Graphics & Audio

- **Graphics**: Sprite sheets from OpenGameArt.org
- **Music**: Royalty-free loop from Joshua Empyre
- **Sound Effects**: Various SFX for gameplay feedback

## Code Structure

- **Object-Oriented Design**: Classes for Ball, Brick, Paddle using inheritance
- **State Pattern**: State machine for managing game states
- **Entity System**: Separate classes for game entities (Ball, Brick, Paddle)
- **Collision Detection**: AABB (Axis-Aligned Bounding Box) collision system

## Persistence

- **High Scores**: Saved to `breakout.lst` in LÖVE's default save directory
- **Format**: Plain text with alternating name/score pairs

## Credits

- **Original Game**: Atari (1976)
- **Engine**: LÖVE 2D
- **Graphics**: OpenGameArt.org / buch
- **Music**: Joshua Empyre
- **Class System**: HUMP (vrld)
- **Resolution Management**: LÖVE community

## Installation & Setup

1. Install LÖVE 2D from https://love2d.org/
2. Clone or download this project
3. Run: `love . ` from the project directory
4. Or drag the project folder onto the LÖVE executable

## Future Enhancements

- Power-ups (multi-ball, paddle expansion, slow-motion)
- Boss levels with special brick patterns
- Difficulty modes (Easy, Normal, Hard)
- Leaderboard system (online)
- Sound options (mute/volume control)
- Achievements and statistics tracking

## License

This is a remake/tribute to the classic Breakout arcade game. Graphics and assets are credited to their respective creators
#
