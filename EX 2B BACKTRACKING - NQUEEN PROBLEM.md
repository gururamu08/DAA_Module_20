# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:16/05/25
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1.Create a Board: Initialize an N x N chessboard with all values set to 0.

2.Check Safety: For each position, check if placing a queen is safe (no other queen in the same row, column, or diagonal).

3.Place a Queen: If the position is safe, place a queen and move to the next column.

4.Use Backtracking: If placing a queen doesn't lead to a solution, backtrack by removing the queen and trying the next position.

5.Print Solution: If all queens are placed safely, print the board. Otherwise, indicate that no solution exists
## Program:
```
Program to implement N-Queen problem using backtracking.
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
def is_Safe(board,row,col,N):
    i = col
    # To check in row
    while(i>=0):
        if board[row][i] == 1:
            return False
        i -= 1
    # To check in upper diagnol
    i = col
    j = row
    while(i>=0 and j>=0):
        if board[j][i] == 1:
            return False
        i -= 1
        j -= 1
    # To check in lower diagnol
    i = col
    j = row
    while(i >= 0 and j < N):
        if(board[j][i] == 1):
            return False
        i -= 1
        j += 1
    return True

def Solve_N_Queens(board,col,N):
    if col >= N:
        return True
    for row in range(N):
        if(is_Safe(board,row,col,N)):
            board[row][col] = 1
            
            if(Solve_N_Queens(board,col+1,N)):
                return True
            board[row][col] = 0
    return False

N = int(input())
board = [[0 for i in range(N)] for j in range(N)]
solution = Solve_N_Queens(board,0,N)
if(solution):
    for i in range(N):
        for j in range(N):
            print(board[i][j],end=" ")
        print()
else:
    print("Solution does not exist")
```

## Output:

![image](https://github.com/user-attachments/assets/42f3d735-14c2-4917-add7-42e01a100be3)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
