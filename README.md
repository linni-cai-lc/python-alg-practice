# Python-Practice

# Week 87 [4/25-5/1]

# 1. [518](https://leetcode.com/problems/coin-change-2/)
```python
def main(amount, coins):
   dp = [0] * (amount+1)
   dp[0] = 1
   for i in coins:
      for j in range(i, amount+1):
         dp[j] += dp[j-i]
   return dp[-1]
```
#### Assumption: N = the number of coins, A = the size of the amount
#### Complexity: runtime = O(N * A), space = O(A)

# 2. [780](https://leetcode.com/problems/reaching-points/)
```python
def main(sx, sy, tx, ty):
   while tx >= sx and ty >= sy:
      if tx == ty:
         break
      elif tx > ty:
         if ty > sy:
            tx %= ty
         else:
            return (tx-sx) % ty == 0
      else:
         if tx > sx:
            ty %= tx
         else:
            return (ty-sy) % tx == 0
   return tx == sx and ty == sy
```
#### Assumption: TX = the size of number tx, TY = the size of number ty
#### Complexity: runtime = O(log(max(TX, TY))), space = O(1 )

# 3. [200](https://leetcode.com/problems/number-of-islands/)
```python
def main(grid):
   LAND = '1'
   WATER = '0'
   DIR = ((-1, 0), (1, 0), (0, -1),(0, 1))
   nrow = len(grid)
   ncol = len(grid[0])
   cnt = 0
   
   def dfs(row, col):
      if 0 <= row < nrow and 0 <= col < ncol and grid[row][col] == LAND:
         grid[row][col] = WATER
         for dr, dc in DIR:
            dfs(row+dr, col+dc)
   
   for row in range(nrow):
      for col in range(ncol):
         if grid[row][col] == LAND:
            cnt += 1
            dfs(row, col)
   return cnt
```
#### Assumption: R = the number of rows, C = the number of columns
#### Complexity: runtime = O(R * C), space = O(R * C) with recursive callstack

### Template
# N. []()
```sql
```

# N. []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)
