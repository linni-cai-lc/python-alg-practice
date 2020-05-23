# Python-Practice
## Week 3 [5.18-5.24]
- [148](https://leetcode.com/problems/sort-list/)
  - divide and conquer
  - recursive merge
  - L < R: L.next = merge(L.next, R) return L
  - L >= R: R.next = merge(L, R.next) return R
  - O(NlogN) `AC`
- [775](https://leetcode.com/problems/global-and-local-inversions/)
  - global/local inversion
  - brute force
    - check A[i] > A[j] for i + 1 < j
    - O(N^2) `TLE`
  - memorize minimum
    - mini = min(mini, A[i])
    - traverse array from right to left
    - find global inversion A[i-2] > mini
    - O(N) `AC`
- [5](https://leetcode.com/problems/longest-palindromic-substring/)
  - palindrome s==s[::-1]
  - brute force
    - traverse all permutations of the string
    - for i in range(len(s))
    - for j in range(i+1, len(s)+1)
    - cur = s[i:j]
    - check cur == cur[::-1]
    - O(N^3) `AC`
  - odd/even center check
    - odd length palindrome
      - L, R = i, i
    - even length palindrome
      - L, R = i-1, i
    - L--, R++
    - compare s[L+1:R] with max_str via `R-L-1 and len(max_str)`
    - expand from center (L,R)
    - O(N^2) `AC`
- [654]()
- [153](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)
  - rotated sort
    - 1,2,3,4 L < M < R min is in [L,M]
    - 4,1,2,3 M < R < L min is in [L,M]
    - 3,4,1,2 R < M < L min is in [M,R]
  - L, R = 0, len(nums)-1
  - loop through nums[L] > nums[R]
    - nums[M] < nums[R]: R=M
    - nums[M] >= nums[R]: L=M+1
  - return nums[L]
  - O(logN) `AC`
- [154](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array-ii/)
  - rotated sort with duplicates
  - loop through nums[L] >= nums[R] and L != R
    - nums[M] < nums[R]: R=M
    - nums[M] > nums[R]: L=M+1
    - nums[M] = nums[R]: R--
  - return nums[L]
  - O(logN) `AC`
- [719]()
- [4]()
- [729]()
- [744]()
- [540]()
- [410]()
