Description
This is a single-player Carrom game developed in Unity. The game includes game elements such as a striker, 8 black pucks, 8 white pucks, and 1 red queen. The player can drag the striker to charge the power of the shot and release it in the desired direction. The game follows general physics rules, including the collisions between the pucks and the striker. The game board has boundaries where the striker and pucks bounce off when they collide. Scoring is implemented using functional pockets on the game board. Each white puck(for player) added to a pocket increases the score by 1, whereas each black puck increases the score by 1 for enemy(AI) and potting the queen adds 2 points. The game also includes a 2-minute timer, and when the timer runs out, a "Game Over" banner is displayed. Additionally, the game features an AI functionality where a bot is capable of taking simple shots.

Screenshots
Screenshot 1 Screenshot 2 Screenshot 3 Screenshot 4 Screenshot 5
Enemy AI
The EnemyTurn() coroutine controls the AI player's actions during its turn. Here's a brief explanation of the steps it performs:

The AI selects a valid position for the striker to hit a coin, attempting to find an unobstructed position within a limited number of attempts.
If a valid position is found, the AI places the striker at that position and checks for any obstructions using a circle overlap check.
If an obstruction is detected, the AI repeats the process until a valid position is found or the maximum attempts are reached.
Once a valid position is determined, the striker's sprite renderer is enabled.
The AI identifies the closest black puck to the nearest pocket based on distance.
The AI calculates the direction and speed at which the striker should hit the target coin.
The calculated force is applied to the striker, propelling it towards the target coin.
The coroutine waits until the striker's velocity drops below a threshold, indicating it has come to rest.
The AI's turn ends, and control is returned to the player.
Player Controls
The player controls are handled by three methods OnMouseDown(), OnMouseDrag() and OnMouseUp():

OnMouseDown() enables the helper arrow sprite.
OnMouseDrag() controls the size and direction of the sprite.
OnMouseUp() controls the force amount by which the striker should shoot. The force is clamped to make sure the player isn't able to exceed a certain threshold. Since this is a coroutine it waits till the striker comes to a stop and then switches the turn to the enemy(AI).
Additional Features
A functioning pause menu, has the option to restart/exit the game.
Sound system for collisions/scoring. Timer sound when the time is less than 10 seconds to make the player aware.
Board sprite always renders at max width accoring to device width.
Fade-in/Fade-out animation on scene change.
Instructions pop-up only on first time load.(Uses PlayerPrefs to implement the same)
Setup
Clone the repository or download the project files.
Open the project in Unity (Unity version used 2023.1.0).
Ensure the necessary assets and references are attached and imported correctly.
Set the desired build settings for Android.
Build and run the game on an Android device or emulator.
Controls
Drag the striker behind to charge the power of the shot.
Release the striker to shoot it in the desired direction.
Tap on the screen to navigate through menus.
Game Rules
The objective of the game is to pot all the pucks while scoring the highest points.
Puck scoring: Each puck added to a pocket increases the score by 1.
Queen scoring: Potting the red queen adds 2 points to the score.
The game lasts for 2 minutes. When the timer runs out, the game ends.
The AI bot takes simple shots and competes against the player.
Dependencies
Unity 2023.1.0
TMPro
