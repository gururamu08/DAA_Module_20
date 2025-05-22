# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:16/5/25
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1.Initialize the maze as a 4x4 grid, where 1 represents open paths and 0 represents blocked paths.

2.Create a solution grid to track the path taken in the maze.

3.Check if the current position is safe (within bounds and not blocked).

4.Use recursion to try moving right or down from the current position, marking the path taken.

5.Print the solution path if the destination is reached, or print "Solution doesn't exist" if there's no valid path.
## Program:
```
Program to implement Rat in a Maze.
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
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
    if x == N-1 and y == N-1:
        sol[x][y] = 1
        return True
    if isSafe(maze,x,y) == True:
        sol[x][y] = 1
        if solveMazeUtil(maze,x+1,y,sol) == True:
            return True
        if solveMazeUtil(maze,x,y+1,sol) == True:
            return True
        s[x][y] = 0
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

![image](https://github.com/user-attachments/assets/8e7db72f-e23a-4f40-b0a1-a9ed033109ec)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
