# PRD: Snake Game

## 1. Overview
This feature adds a new browser-based Snake game to the repository as a single-file HTML project. The game will be easy to run in a browser, use simple keyboard controls, and include a lightweight scoring system without any external dependencies.

The goal is to create a fun, familiar childhood arcade game that fits the same pattern as the existing memory game: a single HTML file with CSS and JavaScript, easy to understand, and easy to play.

## 2. Objective
Build a Snake game that:
- works in a browser without installation
- uses a single HTML file for structure, styles, and logic
- supports keyboard controls for movement
- tracks score and best score
- includes a restart flow and game-over state
- does not break or interfere with the existing memory game project

## 3. Problem Statement
The repository currently contains a memory game, but the user wants a second simple browser game with the same lightweight structure. Snake is a classic arcade game that is easy to learn, fun to play, and fits the repository style.

## 4. User Story
As a player,
I want to play Snake in the browser,
so that I can enjoy a simple, fast arcade game with easy controls and score tracking.

## 5. Scope
### In Scope
- single-page Snake game UI
- keyboard controls using arrow keys or WASD
- score and best score logic
- food spawning and collision detection
- restart and pause support
- responsive game board layout

### Out of Scope
- multiplayer support
- sound effects
- backend storage
- mobile swipe controls at launch

## 6. Functional Requirements
### 6.1 Game Board
The game must display a playable board grid with a visible snake and food item.

Requirements:
- board should be square or near-square
- snake should render clearly on the grid
- food should appear in a random empty cell

### 6.2 Movement
The snake must move continuously once the game starts.

Requirements:
- arrow keys and WASD should move the snake
- movement direction cannot immediately reverse into the snake's body
- the game should update on a regular timed interval

### 6.3 Food and Scoring
The player earns points when the snake eats food.

Requirements:
- each food item increases the score
- the snake grows after eating
- the game speed may increase slightly as score increases
- the best score should persist in local storage

### 6.4 Game Over
The game must end when the snake collides with a wall or itself.

Requirements:
- a game-over message should display
- the player should be able to restart the game
- the score should remain visible

### 6.5 Controls
The app should provide clear controls for play.

Requirements:
- Start / Restart button
- Pause / Resume button
- keyboard controls for gameplay

## 7. Non-Functional Requirements
### 7.1 Simplicity
- the code should remain easy to read and maintain
- no dependencies should be required

### 7.2 Performance
- game updates should feel smooth and responsive
- no lag during normal gameplay

### 7.3 Accessibility
- controls should be keyboard usable
- visible text should remain clear against the background

## 8. UI/UX Requirements
- the game should feel playful and arcade-like
- controls should be easy to locate
- the board should remain readable on desktop and smaller screens
- the page should feel consistent with the existing game style

## 9. Acceptance Criteria
The feature is considered complete when all of the following are true:

1. A playable Snake game loads in the browser.
2. The player can start the game using a button or key input.
3. The snake responds to keyboard input correctly.
4. Food spawns in valid locations and the snake grows after eating it.
5. The score and best score update correctly.
6. Collisions with walls or the snake itself trigger a game-over state.
7. The player can restart the game after losing.
8. The page remains functional without console errors.

## 10. Implementation Notes
A lightweight implementation can use:
- CSS Grid for the board
- JavaScript arrays for snake segments and movement
- localStorage for best score persistence
- a timed game loop with setInterval or requestAnimationFrame

This is a low-risk addition because it is self-contained and independent from the existing memory game logic.

## 11. Risks and Mitigations
### Risk: Direction handling causes invalid reversals
Mitigation: prevent immediate reversal by comparing the new direction against the current direction.

### Risk: Snake overlaps food or walls after growth
Mitigation: generate food only in empty spaces and check collisions before each move.

### Risk: Game speed feels poor
Mitigation: tune the interval and slightly increase speed on score growth.

## 12. Definition of Done
The Snake game is done when:
- it loads and plays in the browser
- the controls work reliably
- score tracking works correctly
- the restart flow functions after losing
- the app is ready to be played by a user without setup issues

## 13. Sign-off
This PRD defines the scope and success criteria for the Snake game. Once implemented, the user should be able to open the page and play immediately without additional setup.
