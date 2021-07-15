# Python-Practice

# Week 62 [11/1-11/7]

# [130](https://leetcode.com/problems/surrounded-regions/)
```python
def main(board):
   nrow = len(board)
   ncol = len(board[0])
   for row in range(nrow):
      for col in (0, ncol-1):
            if board[row][col] == 'O':
               dfs(board, row, col, nrow, ncol)
   for col in range(ncol):
      for row in (0, nrow-1):
            if board[row][col] == 'O':
               dfs(board, row, col, nrow, ncol)
   for row in range(nrow):
      for col in range(ncol):
            cur = board[row][col]
            if cur == 'O':
               board[row][col] = 'X'
            elif cur == 'N':
               board[row][col] = 'O'
   
   
def dfs(board, row, col, nrow, ncol):
   if board[row][col] == 'O':
      board[row][col] = 'N'
      DIR = ((1, 0), (-1, 0), (0, 1), (0, -1))
      for dr, dc in DIR:
         nr, nc = row+dr, col+dc
         if 0 <= nr < nrow and 0 <= nc < ncol:
            if board[nr][nc] == 'O':
               dfs(board, nr, nc, nrow, ncol)
```
#### Assumption: M, N = the matrix dimensions
#### Complexity: runtime = O(MN), space = O(MN)
```python
def main(board):
   nrow = len(board)
   ncol = len(board[0])
   for row in range(nrow):
      for col in range(ncol):
         if row in (0, nrow-1) or col in (0, ncol-1) and board[row][col] == 'O':
            self.dfs(board, row, col, nrow, ncol)
   for row in range(nrow):
      for col in range(ncol):
            cur = board[row][col]
            if cur == 'O':
               board[row][col] = 'X'
            elif cur == 'N':
               board[row][col] = 'O'
   
   
def dfs(board, row, col, nrow, ncol):
   if board[row][col] == 'O':
      board[row][col] = 'N'
      DIR = ((1, 0), (-1, 0), (0, 1), (0, -1))
      for dr, dc in DIR:
         nr, nc = row+dr, col+dc
         if 0 <= nr < nrow and 0 <= nc < ncol:
            if board[nr][nc] == 'O':
               dfs(board, nr, nc, nrow, ncol)
```
#### Note: reduce for-loop code redundancy, merge into one nested for-loop
#### Assumption: M, N = the matrix dimensions
#### Complexity: runtime = O(MN), space = O(MN)

# [205](https://leetcode.com/problems/isomorphic-strings/)
```python
def main(s, t):
   if len(s) != len(t):
      return False
   idx = 0
   book = {}
   while idx < len(s):
      if s[idx] not in book:
         if t[idx] in book.values():
            return False
         book[s[idx]] = t[idx]
      elif book[s[idx]] != t[idx]:
         return False
      idx += 1
   return True
```
#### Assumption: N = the length of the string
#### Complexity: runtime = O(N), space = O(N)

# [1379](https://leetcode.com/problems/find-a-corresponding-node-of-a-binary-tree-in-a-clone-of-that-tree/)
```python
def main(original, cloned, target):
   return dfs(original, cloned, target)

def dfs(root, cloned, target):
   if not root:
      return
   if root == target:
      return cloned
   left = dfs(root.left, cloned.left, target)
   if left:
      return left
   right = dfs(root.right, cloned.right, target)
   if right:
      return right
```
#### Assumption: N = the number of nodes in the tree
#### Complexity: runtime = O(N), space = O(N) recursion call stack

# [1315](https://leetcode.com/problems/sum-of-nodes-with-even-valued-grandparent/)
```python
def main(root):
   res = [0]
   dfs(root, False, False, res)
   return res[0]

def dfs(root, parent_even, grand_even, res):
   if not root:
      return
   cur_even = root.val % 2 == 0
   dfs(root.left, cur_even, parent_even, res)
   dfs(root.right, cur_even, parent_even, res)
   if grand_even:
      res[0] += root.val
```
#### Assumption: N = the number of nodes in the tree
#### Complexity: runtime = O(N), space = O(N) recursive call stack
```python
def main(root):
   return dfs(root, False, False, 0)

def dfs(root, parent_even, grand_even, res):
   if not root:
      return 0
   cur_even = root.val % 2 == 0
   res += dfs(root.left, cur_even, parent_even, 0)
   res += dfs(root.right, cur_even, parent_even, 0)
   if grand_even:
      res += root.val
   return res
```
#### Note: Utilize DFS cumulative values instead of dynamic list
#### Assumption: N = the number of nodes in the tree
#### Complexity: runtime = O(N), space = O(N) recursive call stack

### Template
# []()
```sql
```

# []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)
