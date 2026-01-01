# Two Sum

**Patterns:** General

## ⏱️ Complexity
- Time: O(n)
- Space: O(1)

## ✅ Solution
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        il = []
        rem = 0
        for i,v in enumerate(nums):
            il.append(i)
            rem = target - v
            for j in range(i+1,len(nums)):
                # print(j,nums[j],il)
                if nums[j] == rem:
                    il.append(j)
                    return il
            il = []
        return il
```
