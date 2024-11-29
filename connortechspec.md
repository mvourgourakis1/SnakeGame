# Snake Game Tech Specs

**Manos Vourgourakis**

## 1. Architecture
Single-page application (SPA) with three primary screens:
- **Start Screen**: Game settings and start button
- **Game Screen**: Canvas for gameplay
- **Game Over Screen**: Final score and restart button

---

## 2. Technologies
- **HTML**: Page structure
- **CSS**: UI styling (buttons, text, canvas)
- **JavaScript (ES6)**: Game logic, input handling, state management

---

## 3. UI Components

### Start Screen
- **Inputs**: Food count, game speed, snake and food colors, game mode
- **Button**: Start game

### Game Screen
- **Score display**
- **Canvas**: Displays snake, food, obstacles

### Game Over Screen
- **Final score display**
- **Button**: Restart game

---

## 4. Game Logic

### Main Concepts
- **Snake**: Array of segments, moves by adding a head and removing tail segment unless eating food.
- **Food**: Array of items, each with coordinates. Snake grows and score increments on collision.
- **Obstacles**: Randomly placed if selected mode. Colliding with one ends game.
- **Game Speed**: Adjustable by `gameSpeed` variable controlling loop interval.

### Game Phases
1. **Initialization**: Resets state on "Start Game"
2. **Game Loop**: Redraws game elements, checks collisions
3. **Game Over**: Ends game on collision, clears interval, shows score
4. **Restarting**: Reloads page on "Play Again"

---

## 5. Game Features

### Customizable Settings
- **Food Count**: 1–10
- **Game Speed**: Slow, regular, fast
- **Snake/Food Color**: Red, Orange, Yellow, Green, Blue, Purple, Pink
- **Game Mode**: Classic or Obstacles mode

### Canvas & Background
- **Canvas Size**: 400x400px
- **Background**: Light blue checkerboard pattern (#ADD8E6 and #B0E0E6)

---

## 6. JavaScript Functions

### Initialization
- `startGame()`: Sets initial game state
- `generateFoodItems(count)`: Places food randomly
- `generateObstacles()`: Adds 14 obstacles in Obstacles mode

### Game Loop
- `drawGame()`: Redraws background, obstacles, food, snake; checks collisions

### User Input
- `changeDirection(event)`: Updates snake direction based on arrow keys

### End Game
- `endGame()`: Stops game, shows Game Over screen

### Restart Game
- `restartGame()`: Reloads page

---

## 7. Error Handling and Edge Cases
- **Invalid Input**: Food count limited to 1-10.
- **Collisions**: Detected with walls, self, obstacles; ends game if triggered.

---

## 8. Performance Considerations
- **Game Loop**: Managed by `setInterval()`, clears canvas and redraws each frame.

---

## 9. User Interface/UX Considerations
- **Instructions**: Clear start screen guidance.
- **Score Display**: Shows current score.
- **Difficulty**: Adjustable via speed, food count, obstacles.
