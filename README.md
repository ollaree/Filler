# Filler Game

*A minimalist, two-player, turn-based strategy game inspired by the "Filler" game from GamePigeon. This version is built with plain HTML, CSS, and JavaScript, featuring a retro, terminal-like aesthetic designed for desktop play.*

---

## Description

The objective of the game is to capture more than half of the cells on the board. Players start at opposite corners (Player 1 at the bottom-left, Player 2 at the top-right) and take turns selecting a color to expand their territory. The game ends when all cells on the board are owned by a player.

---

## Functionalities

- **Two-Player Gameplay**: Hot-seat mode for two players on the same computer.
- **Turn-Based System**: Players take turns to choose a color.
- **Dynamic UI**: The status bar updates in real-time to show current scores and whose turn it is, with a blinking cursor effect for the active player.
- **Interactive Color Picker**: Players select colors from a set of buttons. Unavailable colors (the player's own current color and the opponent's) are disabled.
- **Game Over State**: When the board is full, a modal appears declaring the winner and showing the final scores.
- **Restartable**: Players can start a new game at any time after the game ends.
- **Introductory Modal**: A pop-up explains the rules before the first game begins.

---

## How It Works

The game is a single HTML file containing all the necessary CSS for styling and JavaScript for logic.

### Initialization (`init` function):

- When the page loads, the `init()` function is called.
- It sets up the game state, including the grid size and color palette.
- It dynamically creates the grid cells (`<div>` elements) and the color picker buttons.
- The starting cells for Player 1 and Player 2 are assigned, ensuring they begin with different colors.

### Game State:

- A 2D array named `grid` holds the state of each cell (its color, owner, and a reference to its DOM element).
- A `playerState` object tracks the current color and score for each player.
- A `currentPlayer` variable keeps track of whose turn it is.

### Gameplay Loop:

1. A player clicks a color button.
2. The `handleColorChoice` function is triggered. It checks if the move is valid (i.e., not the current color of either player).
3. The player's color is updated to the chosen color.
4. A **flood fill** algorithm is executed. It starts from all cells currently owned by the player and expands outwards, capturing any adjacent, unowned cells that match the newly chosen color.
5. Scores and the UI are updated.
6. The game checks if the board is full. If so, a winner is declared. Otherwise, the turn is passed to the other player.

---

## How to Play

1. Open the `index.html` file in a web browser.
2. Read the instructions on the initial pop-up and click **"Start Game"**.
3. **Player 1** (starting bottom-left) chooses a color from the selection at the bottom to begin capturing adjacent territory.
4. **Player 2** (starting top-right) then chooses a color.
5. Players continue taking turns.
6. You **cannot** choose the color your opponent currently has, or the color you already have.
7. The game ends when all the squares are filled. The player with the most squares wins.
8. Click **"Play Again"** on the game-over screen to start a new match.

---

## AI
AI was used to assist throught all phases of the project
