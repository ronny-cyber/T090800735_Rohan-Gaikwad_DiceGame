﻿# T090800735_Rohan-Gaikwad_DiceGame
This project is an interactive, web-based Ludo game designed for two players. It's built using a combination of web technologies to deliver a complete gaming experience:

I. Core Components & Structure

index.html 📄: This file provides the foundational HTML structure for the Ludo game. It contains:
A div with the class ludo-container that serves as the main wrapper for the game board.
A div with the class ludo which visually represents the game board.
player-pieces for two players (P1 and P2), with each player having four individual pieces defined.
player-bases for both players, indicating their starting areas.
A footer section that includes game controls: a "Roll" dice button, a display for the dice value, a "Reset" button, and a visual indicator for the "Active Player".
Links to style.css for styling and main.js for the game's JavaScript logic.
II. Visuals & Styling

style.css 🎨: This stylesheet dictates the aesthetic presentation of the Ludo board and its various elements. Key styling aspects include:

Defining the ludo-container and the ludo board, utilizing ludo-bg.jpg as the background image.
Styling the player-piece elements, covering their size, borders, border-radius, positioning, and smooth transitions.
Implementing a highlight class for player pieces, adding a cursor: pointer and a spinning animation when active.
Setting distinct background colors for player pieces based on their player-id (e.g., #2eafff for P1, #00b550 for P2).
Styling the player-base elements, including their dimensions, borders, and position.
Adding an animation named border-blink to player-base elements when highlighted.
Styling for general buttons (.btn), the "Roll" button (.btn-dice), and the dice-value display.
ludo-bg.jpg 🖼️: This image file serves as the visual background for the Ludo game board.

III. Game Logic & Functionality

main.js ⚙️: This serves as the entry point for the game's JavaScript, importing and instantiating the Ludo class to begin the game.

Ludo.js 🧠: This file encapsulates the core game logic and mechanics. It manages:

currentPositions: Tracks the positions of all pieces for both players.
_diceValue: Stores and updates the value rolled on the dice, also updating the UI.
_turn: Manages whose turn it is to play, updating the UI accordingly.
_state: Controls the current state of the game (e.g., DICE_NOT_ROLLED, DICE_ROLLED), enabling/disabling the dice and highlighting pieces based on the state.
constructor(): Initializes the game by setting up event listeners for dice clicks, reset clicks, and piece clicks.
onDiceClick(): Handles the dice roll, generates a random value, sets the game state, and checks for eligible pieces.
checkForEligiblePieces(): Determines which pieces can be moved by the current player based on the dice value.
getEligiblePieces(): Filters and returns an array of pieces that are eligible for movement.
incrementTurn(): Switches the active player's turn.
resetGame(): Resets all pieces to their base positions and reinitializes the game state.
onPieceClick(): Handles user clicks on player pieces, validating clicks and initiating piece movement.
setPiecePosition(): Updates the internal position of a piece and visually moves it on the board.
movePiece(): Animates the movement of a piece step by step, checking for win conditions and kills.
checkForKill(): Determines if a piece has landed on an opponent's piece (and if it's not a safe position), sending the opponent's piece back to its base.
hasPlayerWon(): Checks if all of a player's pieces have reached their home positions.
incrementPiecePosition() and getIncrementedPosition(): Calculate the next position for a piece during movement, handling turning points and looping around the board.
constants.js 📊: This file defines crucial constant values used throughout the game logic. It includes:

COORDINATES_MAP: A mapping of game board positions to their visual coordinates.
STEP_LENGTH: Defines the length of each step a piece takes on the board.
PLAYERS: An array listing the player IDs (P1, P2).
BASE_POSITIONS: The initial positions of pieces for each player.
START_POSITIONS: The starting track positions for each player.
HOME_ENTRANCE: The entry points to the home stretch for each player.
HOME_POSITIONS: The final home position for each player.
TURNING_POINTS: Specific positions where pieces turn towards their home entrance.
SAFE_POSITIONS: An array of positions where pieces are safe from being killed.
STATE: An object defining the possible states of the game (e.g., DICE_NOT_ROLLED, DICE_ROLLED).
UI.js 🖥️: This module manages all interactions with the User Interface. It provides static methods for:

Listening for clicks on the dice button, reset button, and player pieces.
Setting the visual position of a player piece on the board.
Updating the display to show the current active player.
Enabling and disabling the dice roll button.
Highlighting and unhighlighting eligible player pieces on the board.
Setting the displayed value of the dice.
