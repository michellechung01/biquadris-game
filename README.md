# Biquadris

Biquadris is a two-player, turn-based falling-block puzzle game inspired by Tetris, featuring multiple difficulty levels, special gameplay effects, and both text and graphical interfaces.

Developed as the final project for CS246: Object-Oriented Software Development at the University of Waterloo, the project emphasizes modular design, abstraction, inheritance, polymorphism, and event-driven game mechanics.

## Features

- Two-player competitive gameplay with independent game boards
- Five difficulty levels (0–4), each with unique block generation rules
- Random and deterministic block generation modes
- Special challenge effects that can be applied to opponents:
  - **Blind** -- obscures part of the opponent's board
  - **Heavy** -- forces blocks downward after movement
  - **Force** -- replaces the opponent's current block
- Complete movement and rotation system
- Line-clearing and score-tracking mechanics
- Turn-based game flow
- High-score tracking throughout the game session
- Text-based and X11 graphical displays
- Modular architecture built using C++20 Modules

## Technologies

- **C++20 (Modules TS)**
- **X11 Graphics Library**
- **GCC 14 / GCC 15**
- **Make Build System**

## Gameplay

![Biquadris Gameplay](https://github.com/user-attachments/assets/0b25e795-69c8-49d4-9e13-6fe9af4a0ac9)

### Objective

Players take turns controlling falling blocks on separate boards. The objective is to survive longer than your opponent by clearing rows, scoring points, and strategically applying challenge effects to disrupt their gameplay.

The game ends when a player can no longer place a new block on their board.

### Scoring

Points are awarded for:

- Clearing one or more complete rows
- Completely removing blocks that were generated at higher difficulty levels
- Clearing multiple rows simultaneously for larger score bonuses

### Special Effects

When a player clears two or more rows in a single turn, they may choose one of the following effects to apply to their opponent:

- **Blind**: Hides a portion of the board until the next block is dropped.
- **Heavy**: Causes the current block to fall additional rows whenever it is moved.
- **Force**: Forces the opponent's current block to become a block type of the attacker's choosing.

### Commands

| Command | Description |
|----------|-------------|
| `left` | Move block left |
| `right` | Move block right |
| `down` | Move block down |
| `clockwise` | Rotate block clockwise |
| `counterclockwise` | Rotate block counterclockwise |
| `drop` | Instantly drop the current block |
| `levelup` | Increase difficulty level |
| `leveldown` | Decrease difficulty level |
| `random` | Enable random block generation |
| `norandom file` | Use a deterministic sequence file |
| `restart` | Restart the game |

## Design Highlights

- Object-oriented architecture built around encapsulation, inheritance, and polymorphism
- Modular game engine implemented using C++20 Modules
- Separation of gameplay logic, display systems, and input processing
- Extensible effect system that allows new gameplay modifiers to be added with minimal changes
- Level-based block generation strategy implemented through polymorphic level classes
- Clear division of responsibilities between game management, players, boards, blocks, effects, and display components

## Building

```bash
make
```

## Running

```bash
./biquadris
```

Example:

```bash
./biquadris -startlevel 2 -seed 42
```
