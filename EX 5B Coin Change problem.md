# EX 5B Coin Change Problem
## DATE: 30/03/2025
## AIM:
To compute the fewest number of coins that we need to make up the amount given.

## Algorithm
1. Read integer n (number of coin denominations).
2. Read integer amt (target amount).
3. Read n coin values into a list s.
4. Initialize a DP array dp of size amt + 1 with all values as infinity.
5. Set dp[0] = 0 (base case: 0 coins to make amount 0).
6. For each coin in s:
   1. For each amount i from coin to amt:
   2. Update dp[i] = min(dp[i], dp[i - coin] + 1)
7. If dp[amt] is not infinity, return dp[amt] (minimum coins needed); else return -1..   

## Program:

### Create a python function to compute the fewest number of coins that we need to make up the amount given.
### Developed by: GOKULA PRIYA P
### Register Number: 212222040044
```
class Solution(object):
   def coinChange(self, coins, amount):

       dp = [float('inf')] * (amount + 1)
       dp[0]=0
       for coin in coins:
           for i in range(coin, amount + 1):
               dp[i] = min(dp[i], dp[i - coin] + 1)
       return dp[amount] if dp[amount]!=float('inf') else -1
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))


print(ob1.coinChange(s,amt))
```
## Output:
![Screenshot 2025-05-24 200347](https://github.com/user-attachments/assets/f084cf50-d70a-451e-be2b-5948fda46752)


## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
