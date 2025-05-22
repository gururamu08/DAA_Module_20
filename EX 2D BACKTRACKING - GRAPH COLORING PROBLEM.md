# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:16/5/25
## AIM:
Given an undirected graph and a number m, determine if the graph can be coloured with at most m colours such that no two adjacent vertices of the graph are colored with the same color. Here coloring of a graph means the assignment of colors to all vertices.



## Algorithm
1. Initialize the Graph: Create a graph with a given number of vertices (V) and a matrix to represent edges.

2.Check Safe Coloring: For each vertex, check if a color can be safely assigned without conflicting with its neighbors.

3.Recursive Coloring: Try assigning colors to the vertices recursively using backtracking. If a conflict arises, backtrack and try another color.

4.Base Case: If all vertices are successfully colored, return True indicating that the coloring is valid.

5.Print Result: If a solution exists, print the assigned colors for each vertex; otherwise, print that no solution exists. 

## Program:
```
Program to implement Graph Coloring Problem using backtracking.
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
class Graph:
    def __init__(self,vertices):
        self.V = vertices
        self.graph = [[0 for col in range(vertices)]for row in range(vertices)]
    
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[i][v] == 1 and colour[i] == c:
                return False
        return True
    
    def graphColourUtil(self,m,colour,v):
        if v == self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c) == True:
                colour[v] = c
                if self.graphColourUtil(m,colour,v+1) == True:
                    return True
            colour[v] = 0
    
    def graphColouring(self,m):
        colour = [0] * self.V
        if self.graphColourUtil(m,colour,0) == None:
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c,end = " ")
        return True

```

## Output:

![image](https://github.com/user-attachments/assets/eaba5c5e-b2ae-4780-9513-6a3659c7da65)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
