# Technical Specification for Snake Game Code

---

## Overview

This project is a simple implementation of the classic *Snake Game* using the Godot Engine. The game logic involves controlling a snake on a grid, eating food items to grow the snake, and avoiding collisions with the grid boundaries or the snake itself. The game supports score tracking and restarts upon game over.

---

## Features

1. **Core Gameplay:**
   - Move the snake in four directions (up, down, left, right) using keyboard input.
   - Collect food items to grow the snake and increase the score.
   - End the game if the snake collides with itself or the grid boundaries.

2. **Game Components:**
   - **Snake**: Made up of individual segments managed in a grid system.
   - **Food**: Appears randomly on the grid and relocates after being eaten.
   - **Score**: Updates and displays in real time.

3. **Game States:**
   - **Main Menu**: Initial screen for starting the game.
   - **In-Game**: Gameplay state with score tracking.
   - **Game Over**: Displays after the game ends, offering options to restart.

4. **Customization:**
   - Grid size (`cells`) and cell dimensions (`cell_size`) can be modified.
   - Snake movement speed is controlled by a timer node (`MoveTimer`).

---

## Code Breakdown

### Variables

- **Game Variables:**
  - `score`: Tracks the player's current score.
  - `game_started`: Boolean indicating if the game is in progress.

- **Grid Variables:**
  - `cells`: Number of cells along each axis of the grid.
  - `cell_size`: Size of each cell in pixels.

- **Snake Variables:**
  - `snake_data`: Array storing positions of snake segments.
  - `snake`: Array of snake segment nodes.
  - `start_pos`: Initial position of the snake.
  - `move_direction`: Direction the snake is moving.

- **Food Variables:**
  - `food_pos`: Position of the current food item.
  - `regen_food`: Boolean controlling food generation.

---

### Functions

- **Setup Functions:**
  - `_ready()`: Entry point; initializes the game.
  - `new_game()`: Resets the game state and initializes the snake and food.
  - `generate_snake()`: Spawns the initial snake at a fixed position.
  - `add_segment(pos)`: Adds a new segment to the snake.

- **Gameplay Functions:**
  - `move_snake()`: Handles movement and input for the snake.
  - `_on_move_timer_timeout()`: Advances the snake, handles collisions, and updates game logic.
  - `check_out_of_bounds()`: Ends the game if the snake leaves the grid.
  - `check_self_eaten()`: Ends the game if the snake collides with itself.
  - `check_food_eaten()`: Checks if the snake eats food and updates the score.
  - `move_food()`: Places a new food item randomly on the grid.

- **Utility Functions:**
  - `end_game()`: Handles game-over state, pauses the game, and shows the Game Over menu.
  - `_on_game_over_menu_restart()`: Restarts the game after a game over.

---

### Signals

- `MoveTimer.timeout`: Triggers `_on_move_timer_timeout` to update game logic periodically.

---

### UI Elements

- **Hud**: Displays the current score.
- **GameOverMenu**: Allows restarting the game after a loss.
- **MainMenu**: Displays initial options to start the game.

---

## Key Algorithms

1. **Snake Movement:**
   - Snake head position is updated based on the current `move_direction`.
   - Remaining segments follow the position of the segment ahead of them (`old_data` array).

2. **Food Placement:**
   - Food is placed randomly within the grid while avoiding overlap with the snake's body.

3. **Collision Detection:**
   - **Boundaries**: Snake's head position is checked against grid limits.
   - **Self-Collision**: Snake's head is compared with the positions of its segments.

---

## Data Flow

1. **Initialization:**
   - `new_game()` resets all game variables and spawns the snake and food.

2. **Frame Updates:**
   - `_process()` listens for input and calls `move_snake()` to handle movement.

3. **Timer Updates:**
   - `_on_move_timer_timeout()` processes snake movement, checks for collisions, and updates the game state.

---

## Configurable Parameters

- `cells`: Adjust grid resolution.
- `cell_size`: Change the size of each grid cell.
- `snake_scene`: Allows the use of a custom snake segment scene.

---

## Improvements & Future Enhancements

1. **Multiple Food Items:**
   - Support multiple food items on the board simultaneously.
2. **Customizable Settings:**
   - Allow players to modify game parameters like speed, grid size, and initial snake length via a settings menu.
3. **Power-Ups:**
   - Introduce special food items for temporary boosts or penalties.
4. **High Score System:**
   - Implement persistent storage for tracking top scores.
5. **Improved Collision Handling:**
   - Use area nodes or signals for cleaner collision detection between snake and food.

---

## Dependencies

- **Godot Engine**: Ensure the project is compatible with the current version being used.
- **Node Structure**:
  - `Main Node`: Root script (`Node`) managing game state and logic.
  - `MoveTimer`: Timer node for controlling movement intervals.
  - `Hud`, `GameOverMenu`, `MainMenu`: UI nodes for user interaction.

---

This specification outlines the current implementation, its features, and areas for improvement. It serves as a guide for maintaining or extending the game.
