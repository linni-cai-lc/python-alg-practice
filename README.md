# Python-Practice

# Week 81 [3/14-3/20]

# [682](https://leetcode.com/problems/baseball-game/)
```python
def main(ops):
   stack = []
   record = 0
   for i in ops:
      score = 0
      if i.isnumeric():
            score = int(i)
      elif i.startswith('-'):
            score = -int(i[1:])
      elif i == 'C':
            if stack:
               last = stack.pop()
               record -= last
               score = 0
      elif i == 'D':
            score = stack[-1] * 2
      elif i == '+':
            score = stack[-2] + stack[-1]
      if score != 0:
            stack += [score]
            record += score
   return record
```
#### Assumption: N = the number of operations in the given list
#### Complexity: runtime = O(N), space = O(N)

# [1995](https://leetcode.com/problems/count-special-quadruplets/)
```python
def main(nums):
   cnt = 0
   size = len(nums)
   for i in range(size):
      for j in range(i+1, size):
         for k in range(j+1, size):
            for l in range(k+1, size):
               if nums[i] + nums[j] + nums[k] == nums[l]:
                  cnt += 1
   return cnt                    
```
#### Assumption: N = the number of elements in the given list
#### Complexity: runtime = O(N^4), space = O(1)

# [2023](https://leetcode.com/problems/number-of-pairs-of-strings-with-concatenation-equal-to-target/)
```python
def main(num, target):
   cnt = 0
   size = len(nums)
   for i in range(size):
      for j in range(i+1, size):
         if nums[i] + nums[j] == target:
            cnt += 1
         if nums[j] + nums[i] == target:
            cnt += 1
   return cnt
```
#### Assumption: N = the number of elements
#### Complexity: runtime = O(N^2), space = O(1)

# [2068](https://leetcode.com/problems/check-whether-two-strings-are-almost-equivalent/)
```python
from collections import Counter
def main(word1, word2):
   book1 = Counter(word1)
   book2 = Counter(word2)
   for i in set(book1.keys()):
      occur_1 = book1[i]
      occur_2 = book2[i]
      if abs(occur_1 - occur_2) > 3:
         return False
      else:
         del book1[i]
         del book2[i]
   for i in book2:
      occur_1 = book1[i]
      occur_2 = book2[i]
      if abs(occur_1 - occur_2) > 3:
         return False
   return True
```
#### Assumption: N = the length of word1/word2
#### Complexity: runtime = O(N), space = O(N)

# [2073](https://leetcode.com/problems/time-needed-to-buy-tickets/)
```python
def main(tickets, k):
   size = len(tickets)
   buy_cnt = size
   cnt = 0
   while buy_cnt > 0:
      buy_cnt = 0
      for idx in range(size):
         val = tickets[idx]
         if val > 0:
            tickets[idx] -= 1
            cnt += 1
            buy_cnt += 1
         if tickets[k] == 0:
            return cnt
```
#### Assumption: N = the number of tickets
#### Complexity: runtime = O(N), space = O(1)

# [1561](https://leetcode.com/problems/maximum-number-of-coins-you-can-get/)
```python
def main(piles):
   piles.sort()
   cnt = 0
   size = len(piles)
   for i in range(size // 3, size, 2):
      cnt += piles[i]
   return cnt
```
#### Assumption: N = the number of elements in the piles
#### Complexity: runtime = O(NlogN), space = O(1)

### Template
# []()
```sql
```

# []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)
