# Assembly Language Snake Game

## Project Team
| BN              | Name                         |
| ----------------| ---------------------------  |
| 01              | Ibrahim Ali Ibrahim Kaldesh  |
| 03              | Ahmed Gamal Saeed Abosalem   |
| 04              | Ahmed Hamdy Mohamed Fahmy    |
| 13              | Aya Osama Sayed Taha         |
| 14              | Passant Amr Ali Hassan       |



## About the project

The idea behind of this program was the classic "Snake" game. This program was made using Microsoft Visual Studio 2019's 32bit MASM architecture in flat mode and the Irvine32 library.

## Features and Functions

### Draw
- First we begin to draw wall and snake.
- we set coordenaties of wall (34,5),(85,5),(34,24),(85,24)
- key symbole of wall is #
- the snake will apper as Xxxxx with its head directed to left but not moving until Player enter any movement key.
- Initial coordenaties of snake is (45,15) for head,(44,15),(43,15),(42,15),(41,15).
- "Your score is 0" will apper in left top of screen and when snake eats a coin it increment score and display it.


#### Game Speed Selection
- User may choose from three speed levels, level 1(fastest) level 2, level 3 (slowest).
- Each of the speed levels have a 40ms difference.
- we implement that by using delay function when moving snake.

#### Random Generation of coin
- A coin is generated randomly at the start of every game or when the snake eats the previous coin and always in the range of coordenaties of wall.
- A checking function is also created to make sure that the random coin does not generate on the coordinates of the snake.
- A new coin is regenerated if the current one is generated at an invalid coordinate.
- Once we get right coordenaties of coin we call DrawCoin to draw coin in this coordenaties.
- Key symbole of coin is X in yellow text.

#### Accepting keyboard input
- After the coin is generated, a loop will be initiated to detect for input and jump to specific functions according to the input.
- If no key is entered, the program will keep looping and waiting for an input.
- If the snake is moving and a valid input is not entered, the function will continuously loop and snake will continuous to move at the current direction.
- If the user enters a new input that moves the snake in a different direction, the program will jump to a function that changes the function of the snake.

#### Move Snake
- The head of the snake will be moved according to the user's last known input.
- The body of the snake will be moved to the coordinate of the unit before it (eg: the 3rd unit of the body will move to the coordinates of the 2nd unit of the body)
- Coin Detection
- When the Snake moves, the coordinate of the head is compared with the coordinate of the coin to check whether the snake eats a coin

#### Eat Coin
- When a coin is eaten, a new unit is added to the snake to lengthen the snake.
- The new tail is at the position of the old tail, a new tail is added according to the direction of the old tail

#### Self Collision Detection
- When the Snake moves, the coordinate of the head is compared with the coordinate of the rest of snake start of unit number 5 to check whether the snake collides with itself
- Snake dies when it collides with itself
- A function loops through the coordinates of the body of the snake and compares with the head position to check if they collide.

#### Wall Collision Detection
- When the Snake moves, the coordinate of the head is compared with the coordinate of the wall to check whether the snake collides with the wall
- Snake dies when it collides with the wall
- A function compares the coordinates of the wall and the head to check if they collide

#### Scoreboard
- When the game is over, a scoreboard is displayed to show the current score and high score of the user.
- The user can also choose to exit the game or restart the game.

#### Input Validation
- Input Validation is set to detect any invalid input and prompts the user to reenter the input if so.
## Flowchart
Flowchart of this program can be downloaded here: [snake game flowchart.pdf](https://github.com/meixinchoy/SnakeGame-asm8086/files/6953798/snake.game.flowchart.pdf)

## Controls
| Keys              | Actions                     |
| ----------------- | --------------------------- |
| w                 | Move up                     |
| a                 | Move left                   |
| s                 | Move down                   |
| d                 | Move right                  |
| x                 | Quits the game at any time  |
| enter             | Pause, (w,a,s,d to unpause) |

(make sure that your capslock is disabled)
