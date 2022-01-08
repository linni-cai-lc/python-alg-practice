# Python-Practice

# Week 86 [4/18-4/24]

# 1. [22](https://leetcode.com/problems/generate-parentheses/)
```python
def main(n):
   res = []
   stack = []
   def backtrack(left, right):
      nonlocal res, stack
      if len(stack) == 2 * n:
         res += ["".join(stack)]
         return
      if left < n:
         stack += ["("]
         backtrack(left+1, right)
         stack.pop()
      if right < left:
         stack += [")"]
         backtrack(left, right+1)
         stack.pop()
   backtrack(0, 0)
   return res
```
#### Assumption: N = the given number size
#### Complexity: runtime = O(4^N/N^1/2), space = O(4^N/N^1/2)

# 2. [198](https://leetcode.com/problems/house-robber/)
```python
def main(nums):
   if not nums:
      return 0
   size = len(nums)
   rob_next = nums[-1]
   rob_next_next = 0
   for i in range(size-2, -1, -1):
      cur = max(rob_next, nums[i] + rob_next_next)
      rob_next_next = rob_next
      rob_next = cur
   return rob_next 
```
#### Assumption: N = the number of elements
#### Complexity: runtime = O(N), space = O(1)

# 3. [55](https://leetcode.com/problems/jump-game/)
```python
def main(nums):
   size = len(nums)
   dp = [False] * size
   for i in range(size-2, -1, -1):
      maxi = min(size-1, i+nums[i])
      for j in range(i+1, maxi+1):
         if dp[j]:
            dp[i] = True
            break
   return dp[0]
```
#### Assumption: N = the number of elements
#### Complexity: runtime = O(N^2), space = O(N)

# 4. [322](https://leetcode.com/problems/coin-change/)
```python
def main(coins, amount):
   dp = [sys.maxsize] * (amount+1)
   dp[0] = 0
   for i in coins:
      for j in range(i, amount+1):
         dp[j] = min(dp[j], dp[j-i]+1)
   if dp[amount] == sys.maxsize:
      return -1
   else:
      return dp[amount]
```
#### Assumption: N = the number of coins, A = the amount size
#### Complexity: runtime = O(N*A), space = O(N)

# 5. [139](https://leetcode.com/problems/word-break/)
```python
def main(s, wordDict):
   wordSet = set(wordDict)
   size = len(s)
   dp = [False] * (size+1)
   dp[0] = True
   for i in range(1, size+1):
      for j in range(i):
         if dp[j] and s[j:i] in wordSet:
            dp[i] = True
            break
   return dp[-1]
```
#### Assumption: N = the given string length
#### Complexity: runtime = O(N^3), space = O(N)

### Template
# N. []()
```sql
```

# N. []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)
