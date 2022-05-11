# Python-Practice

# Week 89 [5/9-5/15]

# 1. [102](https://leetcode.com/problems/binary-tree-level-order-traversal/)
```python
def main(root):
   res = []
        
   def recursiveHelper(cur, level):
      nonlocal res
      if not cur:
            return
      if level == len(res):
            res += [[]]
      res[level] += [cur.val]
      recursiveHelper(cur.left, level+1)
      recursiveHelper(cur.right, level+1)
      
   recursiveHelper(root, 0)
   return res
```
#### Note: recursive method
#### Assumption: N = the number of nodes in the given tree
#### Complexity: runtime = O(N), space = O(N) with recursive callstack
```python
def main(root):
   if not root:
      return []
   res = []
   stack = [(root, 0)]
   while stack:
      cur, level = stack.pop()
      if level == len(res):
         res += [[]]
      res[level] += [cur.val]
      if cur.right:
         stack += [(cur.right, level+1)]
      if cur.left:
         stack += [(cur.left, level+1)]
   return res
```
#### Note: iterative method
#### Assumption: N = the number of nodes in the given tree
#### Complexity: runtime = O(N), space = O(N)

### Template
# N. []()
```sql
```

# N. []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)
