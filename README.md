Download Link: https://assignmentchef.com/product/solved-cs300-homework-1-knight-to-the-rescue
<br>
Brief DescriptionIn this homework, first, you will implement a program that will generate a chessboard of size NxN, where N represents the columns and rows. Then, you will need to implement a function that will place a certain number of pawns on the board based on given conditions. Finally, you will implement another function to place a knight and a king on the chessboard and check if the knight can rescue the king without touching any of the previously placed pawns.To do this homework, you are required to implement a Stack using a LinkedList data structure, i.e., you can not use vectors in the stack implementation. The stack class MUST be template-based. You may want to store basic data types, structs or classes in this stack.Program Flow● Chessboard GenerationThe chessboard will be represented as an NxN 2-dimensional vector (i.e. matrix) where N is going to be an input to your program given by the user. The left bottom of the chessboard will be considered as the (1,1) coordinate. The size of the chessboard must be limited to be in this range 4 &lt; N &lt; 11 where your program must do an input check.We expect each cell of the chessboard to be a stackNode that may contain the following information but you are not limited to storing only these fields, you may keep any other extra fields as needed:1. x_coordinate2. y_coordinate3. visited4. has_pawn● Pawn PlacementOnce the chessboard is generated, you’ll start to place the pawns with the following constraints:● The number of pawns will also be an input to your program and must be limited to be 3N the most where your program must do an input check. For example, if N=8, the number of pawns can be 24 at most.● The first pawn will be placed at coordinate (1,1).● Each pawn following the previous pawn will be placed on a neighbouring cell depending on availability.● On the chessboard, each row, column and diagonal can hold a maximum number of 3 pawns.Once all the pawns are all placed, your program will print out the coordinates of the pawns reading from your stack and also show the chessboard as a matrix.For example, the following placements of 5 pawns on an 8×8 chessboard are invalid because there are 4 pawns on a row in the first picture, on a diagonal on the second and a column on the third picture (your program must avoid such invalid placements):

An example of a valid placement on an 8×8 chess boards with 20 pawns is below, note that there is no row or column or diagonal with more than 3 pawns in this chess board shown below:

The following table shows the first 10 steps of possible pawn placements for a chessboard of size N=8 and p=20 many pawns. The possible cells that one can place each pawn in are shown as red bordered cells below; your program at each step will pick one of these red cells randomly .PlacementTrial Chessboard Available Spaces1Push (1,1)2 Push (1,2)3Push (1,3)

4Push (2,3)5Push (3,3)6Push (2,4)7Push (4,1)

8Push (3,2)9Push (3,1) No More Available SpacesBut we still need to place more pawns10 Pop (3,1) and mark unavailable11Push (2,1) No More Available SpacesBut we still need to place more pawns10 Pop (2,1) and mark unavailable No More Available Spaces that we visited from last-placedpawn (3,2)10 Pop (3,2) and mark unavailable

● Rescuing the King with the KnightAfter the pawns are placed you’ll place your knight and king on two given available cells on the chessboard where the user will input these cell coordinates as input to your program. Then, you’ll check if your knight can rescue the king without touching any of the placed pawns on the chessboard. Then your program will print out the moves done by the knight. If there is no path to your king, then your program should indicate this by printing out “No Way!” .

The knight moves in an “L-shape” — that is, they can move two squares in any direction vertically followed by one square horizontally, or two squares in any direction horizontally followed by one square vertically. Your knight can not move to a cell that’s occupied by the enemy pawn. The following diagrams show the possible moves of a knight on the chessboard:

If your knight faces a deadlock where it can not move further and moves back (similar to the scenario that’s explained for pawns above), this cell should be marked as unavailable. Also in your output, we shouldn’t see moves like knight moves from (1,8) to (2,6) and back to (1,8). You should display the path that the knight takes to reach your king where the steps must not be repeated. That is, there shouldn’t be any same coordinates in this path.Output FormatThe following example is the expected output format. You should write your output to a txt file named output.txt . Please note that the empty lines should be present in your output for it to work with the semi-automated grading tool. We expect N, P, Pawn Locations, Knight and King locations, Knight Moves and the Chessboard matrix (be careful to invert x and y values when you’re printing the matrix out) in your output exactly as they appear below:

N = 8P = 24

Pawn Locations 8 17 16 25 24 35 46 5

7 48 58 67 76 75 84 83 83 74 63 62 52 42 31 31 21 1

Knight = 1 8King = 8 8

1 82 64 73 55 64 46 34 26 15 33 25 17 26 47 68 8

Matrix0 0 1 1 1 0 0 00 0 1 0 0 1 1 00 0 1 1 0 0 0 10 1 0 0 0 1 0 10 1 0 0 1 0 1 01 1 0 1 0 0 0 01 0 0 0 1 1 0 01 0 0 0 0 0 1 1

Sample RunsSample Run 1Please enter the size of the board (n): 8 Please enter the number of the pawns (p): 16 The matrix:0 0 0 1 0 0 0 00 0 1 1 1 0 0 00 1 0 0 1 0 0 00 0 1 0 0 1 0 00 0 0 1 1 1 0 01 1 1 0 0 0 0 01 0 0 0 0 0 0 0 1 0 0 0 0 0 0 0Enter the position of knight(x,y): 1 8 Enter the position of king(x,y): 8 8 No way!

Output FileN = 8P = 16

Pawn Locations6 45 46 55 65 74 84 73 72 63 54 43 32 31 31 21 1

Knight = 1 8King = 8 8No Way!

Matrix0 0 0 1 0 0 0 00 0 1 1 1 0 0 00 1 0 0 1 0 0 00 0 1 0 0 1 0 00 0 0 1 1 1 0 01 1 1 0 0 0 0 01 0 0 0 0 0 0 01 0 0 0 0 0 0 0

Sample Run 2Please enter the size of the board (n): 8Please enter the number of the pawns (p): 140 1 0 0 1 1 0 00 1 1 1 0 0 0 00 0 1 0 0 0 0 00 0 0 1 0 0 0 00 0 0 1 0 0 0 01 1 1 0 0 0 0 01 0 0 0 0 0 0 01 0 0 0 0 0 0 0Enter the position of knight(x,y): 1 8 Enter the position of king (x,y): 8 1 Path found, see the output file!

Output FileN = 8P = 14

Pawn Locations6 85 84 73 72 82 73 64 54 43 32 31 31 21 1

Knight = 1 8King = 8 1

1 82 63 81 72 54 66 55 77 86 67 45 33 22 41 63 55 67 55 44 26 37 15 26 48 36 28 1

Matrix0 1 0 0 1 1 0 00 1 1 1 0 0 0 00 0 1 0 0 0 0 00 0 0 1 0 0 0 00 0 0 1 0 0 0 01 1 1 0 0 0 0 01 0 0 0 0 0 0 01 0 0 0 0 0 0 0

General Rules and Guidelines about Homeworks

The following rules and guidelines will apply to all homework unless otherwise noted.

How to get help?

You may ask questions to TAs (Teaching Assistants) of CS300. Office hours of TAs can be found her e. Recitations will partially be dedicated to clarifying the issues related to homework, so it is to your benefit to attend recitations.