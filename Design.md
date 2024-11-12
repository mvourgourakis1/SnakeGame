# Snake Game Design Specs

**Manos Vourgourakis**

## 1. Game Features

### 1.1 Customization Options
- **Number of Food Items**: Selectable between 1-10.
- **Game Speed**: Options - "Slow," "Regular," or "Fast."
- **Snake Color**: Choices include Red, Orange, Yellow, Green, Blue, Purple, Pink.
- **Food Color**: Choices include Red, Orange, Yellow, Green, Blue, Purple, Pink.
- **Game Mode**: Options - Classic Mode (traditional gameplay) or Obstacles Mode (random obstacles added).

### 1.2 Gameplay
- **Controls**: Arrow keys (Up, Down, Left, Right) control the snake.
- **Snake Movement**: Continuously moves, changes direction with arrow keys.
- **Food**: Eating food increases score by 1 and lengthens the snake by one segment.
- **Obstacles (optional)**: In Obstacle mode, random obstacles are placed on the grid. Colliding with obstacles ends the game.
- **Collisions**: Game ends if the snake collides with walls, itself, or obstacles (in Obstacles mode).

### 1.3 Game Loop
1. Clear Canvas
2. Draw Background (checkerboard pattern)
3. Draw Snake (customizable color)
4. Draw Food (customizable color)
5. Move Snake
6. Check Collisions
7. Update Score
8. End Game if any collision occurs

---

## 2. Game Flow

### 2.1 Start Screen
- **UI Elements**:
  - Welcome message ("Welcome to Snake Game!")
  - Options for food count, speed, colors, and game mode
  - "Start Game" button

### 2.2 Game Screen
- **UI Elements**:
  - Score display
  - Game canvas (background, snake, food, obstacles if applicable)
  
### 2.3 Game Over Screen
- **UI Elements**:
  - "Game Over :("
  - Final score display
  - "Play Again" button

---

## 3. Art and Aesthetics

### 3.1 Art Style
- **Background**: Light blue checkerboard pattern (#ADD8E6 and #B0E0E6).
- **Snake**: Customizable square segments.
- **Food**: Square items with customizable color.
- **Obstacles**: Black squares in Obstacles mode.

### 3.2 User Interface
- **Fonts**: Arial, sans-serif; Score font size - 24px; General text - 12px.

---

## 4. Technical Specifications

### 4.1 Languages and Tools
- **HTML5**: Page structure
- **CSS3**: Styling layout, buttons, UI elements
- **JavaScript**: Game logic, event handling, canvas rendering
- **Canvas API**: Drawing game elements and real-time rendering

### 4.2 Canvas Dimensions
- **Canvas Size**: 400px x 400px
- **Box Size**: 20px per segment

### 4.3 Game Variables
- **Snake Movement**: Tracks head position and updates direction.
- **Collision Detection**: Checks for wall, body, and obstacle collisions.
- **Food Generation**: Random placement, snake grows on consumption.
- **Obstacles**: Randomly placed in Obstacles mode.

### 4.4 Event Handling
- **Keyboard Input**: Arrow keys control the snake’s direction.
- **Start/Restart**: "Start Game" and "Play Again" buttons.

### 4.5 Performance
- Uses `setInterval` to control frame rate.

---

## 5. Game Modes

### 5.1 Classic Mode
- **Rules**: Snake grows by eating food, ends on collision with walls or itself.

### 5.2 Obstacles Mode
- **Rules**: Random obstacles added, snake must avoid collisions with them.

---

## 6. Monetization (Optional)
- **Ad Revenue**: Ads on start and game-over screens.
- **Premium Features**: Cosmetic upgrades for snake and food customization.

---

## 7. Target Audience
- Casual gamers interested in retro arcade games with customization.

---

## 8. Testing
- **Unit Testing**: For collision detection, food generation, score updates.
- **User Testing**: Ensuring enjoyable gameplay and easy-to-use customization options.

---

## 9. Future Updates
- **Leaderboard**: High score tracking.
- **Mobile Support**: Touch controls.
- **Sound Effects**: Eating food, collisions, game over.
