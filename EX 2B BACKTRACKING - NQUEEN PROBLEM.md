# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 04-04-2025
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Start the program.

2. Initialize the Board: Start with an empty N x N chessboard filled with 0s.

3. Check Safety: For each queen placement, ensure no other queen can attack it by checking the row, column, and diagonals.

4. Place Queen: If the current position is safe, place the queen (set the cell to 1) and move to the next column.

5. Backtrack: If placing a queen leads to a conflict later, backtrack by removing the queen and trying the next row.

6. Recursive Search: Continue the process until all queens are placed or return that no solution exists if no valid placement is found.

7. End of program
## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: RAMYA R
Register Number:  212223230169
*/
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col>=N:
        return True
    for i in range(N):
        if isSafe(board ,i,col):
            board[i][col]=1
            if solveNQUtil(board,col+1) == True:
                return True
            board[i][col]=0
    return False 
    
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```

## Output:

![image](https://github.com/user-attachments/assets/241a4573-386b-49ac-8c16-4f21024db332)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
