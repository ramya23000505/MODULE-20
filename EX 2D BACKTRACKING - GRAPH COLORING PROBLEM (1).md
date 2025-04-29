# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Start the program.

2. Initialize a color array color[] with zeros for each vertex.

3. For each vertex, recursively attempt to assign a color from 1 to m.

4. For each color, check if it’s safe to assign (i.e., no adjacent vertex has the same color).

5. If the color is safe, assign it and recursively try to color the next vertex.

6. If all vertices are successfully colored, return the color array.

7. If no color assignment is possible for a vertex, backtrack and try the next color.

8. If a valid coloring configuration is found, print the colors; otherwise, print "Solution does not exist".   

9. End of program.
   
## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: RAMYA R
Register Number:  212223230169
*/

class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]

    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] and colour[i] == c:
                return False
        return True

    def graphColoringUtil(self, m, colour, v):
        if v == self.V:
            return True

        for c in range(1, m + 1):
            if self.isSafe(v, colour, c):
                colour[v] = c
                if self.graphColoringUtil(m, colour, v + 1):
                    return True
                colour[v] = 0
        return False  # Return False if no valid coloring is possible

    def graphColouring(self, m):
        colour = [0] * self.V
        if not self.graphColoringUtil(m, colour, 0):
            print("Solution does not exist")
            return
        
        return colour
            

# Driver code
g = Graph(4)
g.graph = [
    [0, 1, 1, 1],
    [1, 0, 1, 0],
    [1, 1, 0, 1],
    [1, 0, 1, 0]
]
m = 3
colors = g.graphColouring(m)

if colors:
    print("Solution exist and Following are the assigned colours:")
    for c in colors:
        print(c, end=" ")
    print()

```

## Output:
![image](https://github.com/user-attachments/assets/d9b8ab56-c808-4d77-98f6-ad1a5934ef5b)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
