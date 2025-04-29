# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 01-04-2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start the program.

2. Define the maze as a 2D list with 1s (open path) and 0s (blocked path).

3. Create a solution matrix of the same size initialized with 0s.

4. Define a function isSafe() to check if a move to a particular cell is within bounds and not blocked.

5. Define a recursive function solveMazeUtil() that marks the current cell and attempts to move down or right.

6. If the rat reaches the destination cell, mark it and return success.

7. If all moves fail from a cell, backtrack by unmarking it in the solution matrix.

8. Call the recursive function from the start cell and print the solution matrix if a path exists; otherwise, print that no solution exists.  

9. End of program.
## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: RAMYA R
Register Number:  212223230169
*/

N = 4
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     
def solveMazeUtil(maze, x, y, sol):
    # if (x, y is goal) return True
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
        # typecode ****
    if isSafe(maze,x,y) == True:
        sol[x][y] = 1
        if solveMazeUtil (maze, x+1,y, sol) == True:
            return True
        if solveMazeUtil (maze, x, y+1, sol) == True:
            return True
        sol[x][y] =0
        return False
        
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:
![image](https://github.com/user-attachments/assets/93ce2221-df29-4f5d-900e-09f0525223db)



## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
