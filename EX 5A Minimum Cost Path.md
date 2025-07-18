# EX 5A Minimum Cost Path
## DATE: 28/03/2025
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.

## Algorithm
1.  Base Case:If either row (m) or column (n) is out of bounds (i.e., less than 0), return a very large value (sys.maxsize) to signify an 
    invalid path.
2.  If both m == 0 and n == 0, return the cost of the starting cell cost[m][n].
3.  Recursive Case:For every cell (m, n), calculate the minimum cost by considering three possible moves:
4.  Move from the top-left diagonal (m-1, n-1).
5.  Move from the top (m-1, n).
6.  Move from the left (m, n-1).
7.  For each direction, recursively compute the cost and add the current cell's cost.
8.  Return the Minimum Cost:Recursively return the minimum of the three paths, adding the cost of the current cell.
9.  Final Output:Call the recursive function starting from the bottom-right corner of the matrix to find the minimum cost.  

## Program:

### A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.
### Developed by: GOKULA PRIYA P
### Register Number: 212222040044

```
R = int(input())
C = int(input())
import sys
def minCost(cost, m, n):
    if n<0 or m<0:
        return sys.maxsize
    elif(m==0 and n==0):
        return cost[m][n]
    else:
        return cost[m][n]+min(minCost(cost,m-1,n),
                                minCost(cost,m-1,n-1),
                                minCost(cost,m,n-1))
            
    
def min(x, y, z):
    if (x < y):
        return x if (x < z) else z
    else:
        return y if (y < z) else z
cost= [ [1, 2, 3],
        [4, 8, 2],
        [1, 5, 3] ]
print(minCost(cost, R-1, C-1))
```

## Output:
![Screenshot 2025-05-24 200053](https://github.com/user-attachments/assets/73abd944-78d1-49e8-b3b0-098915b8ffef)

## Result:
Thus the above program was executed successfully for finding the minimum cost.
