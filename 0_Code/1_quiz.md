### 268. Missing Number

Link : https://leetcode.com/problems/missing-number/

```
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        nums.sort()
        for i in range(len(nums)):
            if nums[i] != i:
                return i
        return len(nums)
```

```
# Sum of 0..n minus sum of the given numbers is the missing one.
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)
        return int(n * (n+1) /2 - sum(nums))
```

### 222. Count Complete Tree Nodes
Link : https://leetcode.com/problems/count-complete-tree-nodes/

```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def countNodes(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        
        def depthLeft(node):
            d = 0
            while node:
                d += 1
                node = node.left
            return d
        
        def depthRight(node):
            d = 0
            while node:
                d += 1
                node = node.right
            return d
        
        ld = depthLeft(root.left)
        rd = depthRight(root.right)

        if ld == rd:
            return 2**(ld+1) -1
        else:
            return 1 + self.countNodes(root.left) + self.countNodes(root.right)
        
```






