# Minimum Viable Product Priority

## Day 1 - Creating the Level (P0)
- Render a tilemap representing the maximum space the player can navigate.
- Implement `generateFood()`, generating food tiles of different colors that have no behavior for now randomly in the tilemap over time.

## Day 2 - Creating the Snake Player (P0)
- Render the player which consists of a line of tiles of size `int` variable `length`.
- When the player head is in the same position as a food on the map, increment the length of the snake by one. 
- Set a temporary constant speed to which the line of tiles representing the player moves forward
- Detect all user input to `changeDirection()` of the player, the head tile of the player should respond immediately to this change, moving forward in whatever new direction the input says.
- In order to create a continous tail, delay the movement of each tile behind the head of the player by one.

## Day 3 - Creating the Game Loop (P0)
- Implement `handleCollision()` which detects when a player's position is equal to the max tilemap length or width or a position that is a part of the player's body.
-  When the player collides, show a game over UI to allow the player start the game again.

## Day 4 - Adding Different Modes (P1)
- Implement an `enum` called `playerSpeed` which changes the speed at which the player moves forward. This varies the difficulty of the game.
- Implement an `enum` called `gameMode` where players can switch between regular and obstacle mode. In obstacle mode, in addition to generating food constantly in the tilemap, generates obstacles that will end the game if the player head collides with the obstacles.

## Day 5 - Coding Food Behavior (P2)
- Instead of having all food increase the snake length by one, add different features for different colored foods!
- You could make one temporarily increase the snake's speed and make another one that decreases the length of the snake. 
