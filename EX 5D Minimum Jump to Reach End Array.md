# EX 5D Minimum Jump to Reach End Array
## DATE: 08/04/2025
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.

## Algorithm
1. Read integer `n` (number of elements in the array).
2. Read `n` integers into array `arr`.
3. If `n == 0` or `arr[0] == 0`, return infinity (end cannot be reached).
4. Initialize a `jumps[]` array of size `n` with all values `∞` and set `jumps[0] = 0`.
5. For each position `i` from 1 to `n - 1`:

   * For each position `j` from 0 to `i - 1`:

     * If `i` is reachable from `j` (i.e., `i <= j + arr[j]`) and `jumps[j]` is not `∞`:

       * Update `jumps[i] = min(jumps[i], jumps[j] + 1)`
       * Break inner loop (first valid jump found)
6. Return `jumps[n-1]` as the minimum number of jumps to reach the end.   

## Program:

### To implement the program to finding the minimum number of jumps needed to reach end of the array.
### Developed by: GOKULA PRIYA P
### Register Number: 212222040044

```
def minJumps(arr, n):
    jumps = [0 for i in range(n)]
 
    if (n == 0) or (arr[0] == 0):
        return float('inf')
 
    jumps[0] = 0
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if (i <= j + arr[j]) and (jumps[j] != float('inf')):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    return jumps[n-1]
    ##########  Add your code here ##############
arr = []
n = int(input()) #len(arr)
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr,n))
```
## Output:
![Screenshot 2025-05-24 201156](https://github.com/user-attachments/assets/6f7d65ee-b6ee-4deb-b73b-dc5bec96026d)

## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
