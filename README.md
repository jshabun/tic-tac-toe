# AI Tic-Tac-Toe
## Tic-Tac-Toe AI Algorithm Analysis

## Introduction
This is a Tic-Tac-Toe game. The user is Player 1 and the AI is Player 2. The project utilizes a minimax algorithm and a couple optimization techniques (alpha-beta pruning and caching) to make sure that it runs faster than it would with just the base algorithm.

## Algorithm Description
The algorithm chosen for this use case is the minimax algorithm. I figured this was the best algorithm for this use case that would result in a fairly speedy and accurate response time.

The minimax algorithm is a game thoery algorithm used for 2 player games. It is a backtracking algorithm that chooses the best move that yields the highest score for the AI player.

The strengths of this algorithm is that it does ensure that the AI player does make the best possible move during its turn. It makes sure that it has the best score it can have during play. One downturn of this alogirithm, though, is as the tree grows exponentially, it becomes less efficient as it has to traverse the larger tree to find the best move. This leaves the algorithm becoming much slower as moves and time progress, especially for larger games. 

To help alleviate some of that long tree traversal and time, I utilized both caching and alpha-beta pruning. The cache stores the board as a tuple to allow for hashing and the alpha-beta pruning throws away or (prunes) branches that don't make the best moves. 


## Example Scenario
In this scenario, Player 2 (AI) is making a move on a Tic-Tac-Toe board.

To select the best move, Player 2 uses a minimax algorithm with alpha-beta pruning. This algorithm recursively explores all possible board configurations (from both Player 2's and Player 1's perspectives) to determine the optimal move.

The algorithm follows this process:

1. Evaluate the current board configuration for Player 2 (AI) and Player 1.
2. If Player 2 has a winning configuration or the board is full (resulting in a tie), return the evaluation score.
3. Iterate through each empty cell on the board and make a temporary move for Player 2.
4. Recursively call the minimax function to evaluate the board configuration after Player 2's move.
5. Undo the temporary move made in step 3.
6. Select the move that led to the highest score after recursively evaluating all possible board configurations.

During the recursive calls, Player 2 plays optimally to maximize its score while Player 1 plays optimally to minimize its score. The algorithm also includes a transposition table (cache) to store and retrieve previously computed board configurations to reduce the number of recursive calls.

In the code snippet provided, the minimax function is used to implement the minimax algorithm. The `is_winner` and `is_board_full` functions are used to check if Player 2 or Player 1 has won the game and if the board is full.

By utilizing this AI algorithm, Player 2 is able to play a winning or draw-only game of Tic-Tac-Toe.

# Running the Code
1. Open a new terminal window and navigate to the directory where the code is located. ![](/tic-tac-toe/media/2.png)
2. Run `python3 tic_tac_toe.py` in your terminal. 
![](/tic-tac-toe/media/3.png)
3. Once the python files runs, it will either start with Player 1 (you) or Player 2 (AI). ![](/tic-tac-toe/media/4.png)
4. To play: The play area is 3 x 3. To input your move enter the row then column with a space in between then hit enter. ![](/tic-tac-toe/media/5.png)
5. Once the game is over, the program will tell you if you lost, won, or if the game ended in a tie. ![](/tic-tac-toe/media/6.png)

## Conclusion
While working on this project, I noticed a few things. When utilizing the minimax algorithm, the AI played as it should but mushc slower than if you were playing a "computer" in an online game. This meant that the algorithm had to be optimized. 

Researching a few techniques, I found that alpha-beta pruning and caching would be the best for this use-case. As I tested each optimization technique, I first noticed that alpha-beta pruning did speed up the AI player exponentionally than just running the base minimax algoirithm unoptimized. But, the AI was still a bit slow. Then, testing just the caching made the AI a lot faster but it also made it a lot less accurate. When combining the two, it gave me an accurate and speedy AI player that seemed to work well during testing. 