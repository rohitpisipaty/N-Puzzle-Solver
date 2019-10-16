# N-Puzzle-Solver
In this project, we will implement A* for the sliding puzzle game. The game is played on an n x m board. Tiles are arranged in a random order with one spot left empty. A neighboring tile can move to the empty square. The objective of the game is to sort the tiles in increasing order.

As part of the project, we will implement A* search. You will also implement three admissible heuristic functions to guide the A* search.

Heuristic 1 should be the Misplaced Tiles heuristic

Heuristic 2 should be the Manhattan Distance heuristic

Heuristic 3 can be Linear Conflict, Pattern Database, Nilsson's Sequence Score, N-MaxSwap, X-Y, TilesOut (go here for more information on these heuristics). You can also implement your own heuristic, which should perform nearly as well or better than Heuristic 1 or Heuristic 2. Make sure to clearly describe what your heuristic does.

The code supports the following interface

RunPuzzleSolver fnamePuzzle heuristic tmax fnameMoves
where
RunPuzzleSolver is the name of the program
fnamePuzzle is the name of the input file containing the puzzle description
the input file format is as follows:
nrRows nrCols val_0 val_1 ... val_N
where
nrRows specifies the number of rows
nrCols specifies the number of columns
val_i specifies the value of the i-th square, where i ranges from 0 to N=nrRowsxnrCols -1
values are listed row by row, so the i-th square is located in row i / nrCols and column i mod nrCols
heuristic is the name of the heuristic where
H1 is used to denote Heuristic 1
H2 is used to denote Heuristic 2
H3 is used to denote Heuristic 3
tmax is the maximum runtime in seconds
this is an upper limit on the runtime for your A* search. When this time limit is reached, your A* search should stop. If it has not found a solution, it should report failure.
fnameMoves is the name of the file where you should write the moves found by the search
Use 0, 1, 2, 3 for left, right, up, and down moves.
File should be just a sequence of 0, 1, 2, 3 written one per line.For example
0
3
1
1
Support code is provided in C++. The support code provides a graphical interface to display the puzzle and the solution. It also has functionality to generate random configurations for the sliding puzzle game. The support code has placeholders where you can add your heuristic and A* implementations. It already implements the puzzle, including the move functions.

generate random configuration for the sliding puzzle:
./bin/Runner RunRandomPuzzle nrRows nrCols nrRandMoves fnameOut

(on Windows use bin\Debug\Runner instead of ./bin/Runner)

solve the sliding puzzle (you must implement PuzzleSolver and Puzzle Heuristics):
./bin/Runner RunPuzzleSolver fnameBoard heuristic tmax fnameMoves
graphical display:
./bin/Runner GRunPuzzle nrRows nrCols nrRandMoves tmax
once the graphical display is up, press the keys shown below for more functionality:
r : randomize puzzle board
0 : solve puzzle using the zero heuristic
1 : solve puzzle using heuristic1
2 : solve puzzle using heuristic2
3 : solve puzzle using heuristic3
+ : go over the solution one move at a time
p : read puzzle board from file puzzle.txt
m : read moves from file moves.txt
ARROW_LEFT : make left move
ARROW_RIGHT : make right move
ARROW_UP : make up move
ARROW_DOWN : make down move
Follow the directions below for compiling the support code

Support Code: C++ in Linux/Mac OS
Linux: Install cmake, g++, and freeglut

MacOS: Install gcc. The easiest way is to download the Apple Developer Tools from http://connect.apple.com (free, but requires registration). You can also install gcc through a package manager such as MacPorts or Fink

Open terminal and change to the directory where you have placed SupportCode

Run cmake .

Run make

If there are no errors, then everything went fine. You are ready to execute the program

Execute the program as already described

Support Code: C++ in Windows
Install CMake

Install Microsoft Visual C++ Express Edition 2010

Open command prompt and change to the directory where you have placed SupportCode

Run cmake -G "Visual Studio 10"

If you have the latest version, run cmake -G "Visual Studio 15 2017"

Go to the Support folder and double click on the solution file. This will open up Visual Studio

Build the project by going to Project and selecting the Build option

If there are no errors, then everything went fine. You are ready to execute the program

Execute the program as already described
