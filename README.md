# Python-Practice

# Week 37 [5/10-5/16]

# [566](https://leetcode.com/problems/reshape-the-matrix/)
```python
def main(nums, r, c):
    if not nums or not nums[0] or r * c != len(nums) * len(nums[0]):
        return nums
    new_m = [[0] * c for _ in range(r)]
    cur_r = 0
    cur_c = 0
    for i in range(len(nums)):
        for j in range(len(nums[0])):
            new_m[cur_r][cur_c] = nums[i][j]
            cur_c += 1
            if cur_c == c:
                cur_c = 0
                cur_r += 1
    return new_m
```
#### Assumption: M = the number of rows in the given nums matrix, N = the number of columns in the given nums matrix, R = the number size of r, C = the number size of c
#### Complexity: runtime = O(MN), space = O(1) excluding result matrix

### Template
# []()
```sql
```

# []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)