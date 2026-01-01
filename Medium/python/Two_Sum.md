# Two Sum

🔗 https://leetcode.com/problems/two-sum/

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
