# Connect-4-with-Coppeliasim

 ## Different components of the system

Board : Connect 4 board with meshes and a rack at the bottom.

Humanoid: Still robot with two moving arms to put the chip in a certain column. Consist of 4 revolute joints (2 shoulder and 2 wrist) and 2 prismatics joints(1 elbow and 1 for the gripper). Default positions for the arms are above the end of the loader's upper arm.

Top Funnel: Funnel at the top of board to allow some forgiveness for the positions to move the humanoid arms to the exact board column, connected to prismatic joints to allow the movement in case the chips are stuck in board.

Bottom Funnel: To collect the chips after they fall from the board, includes three chip beaters to facilitate the movement of chips in the funnel. It has two prismatic doors at the bottom to allow one chip at a time to fall in for the sorting system.

Sorter: Employs camera to sense the color (essentially the middle pixel value) and based on that it moves the platform to either side for the Loader.

Loader: Left and Right loaders are for loading the yellow and Red chips respectively. Employ 4 proximity sensors, 3 prismatic joints and it runs a logic to make sure that it runs while necessary. Prismatic joint at the bottom shoots the chip up and when the top proximity sensor senses, it extends a ramp to load the chip on the upper arm of the loader so that the humanoid can grab it.

GUI: Virtual interface to see the whole game working and have buttons for New game, Quit, Buttons for all the columns, 2 lamps for the Player’s turn, and lamps for each slot in the board.

## Function:
When New game on the GUI is hit, it opens the rack at the bottom of the board and lets all the chips fall in the bottom funnel. Also triggers the prismatic joints at the top funnel to make sure all the chips leave the board.

Then the sorter system is triggered and it starts the sorting and lines up the chips for both the loaders to load.

When the loader sees that there aren't sufficient chips in the upper arm, it starts to load and shoots the chips.

When a column button is hit, Robot grabs the chip, reads the position for a specific column and moves the Right or Left arm for Red and yellow resp.

In matlab, we keep on populating the matrix to check the winning condition, and if someone wins, it stops the game and does not allow any more buttons to be pressed.

