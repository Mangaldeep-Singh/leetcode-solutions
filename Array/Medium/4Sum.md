# 4Sum

**Difficulty:** Medium  
**Topic:** Array  
**Pattern:** Two Pointers

🔗 https://leetcode.com/problems/4sum/

---

## 📘 Description
Given an array nums of n integers, return an array of all the unique quadruplets [nums[a], nums[b], nums[c], nums[d]] such that:


	0 <= a, b, c, d < n
	a, b, c, and d are distinct.
	nums[a] + nums[b] + nums[c] + nums[d] == target


You may return the answer in any order.

 
Example 1:

Input: nums = [1,0,-1,0,-2,2], target = 0
Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]


Example 2:

Input: nums = [2,2,2,2,2], target = 8
Output: [[2,2,2,2]]


 
Constraints:


	1 <= nums.length <= 200
	-109 <= nums[i] <= 109
	-109 <= target <= 109

---

## 🧠 Intuition
- **Two Pointers**: Use this technique to optimize the solution.

---

## ✅ Solution (Python)
```python
class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        # using two pointers concept by fixing 2 elements and using two pointers
        nums.sort()
        res = []
        n = len(nums)
        for i in range(n-3):    #loop until n-4 ele
            if i > 0 and nums[i] == nums[i-1]:
                # if same numbers set pointer to last occurance of element
                continue
            n1 = nums[i]
            for j in range(i+1,n-2):    #loop upto n-3
                if j > i + 1 and nums[j] == nums[j-1]:
                    continue
                n2 = nums[j]
                left = j + 1
                right = n-1 
                tar = target - n1 - n2
                while left < right:
                    s = nums[left] + nums[right]
                    if s == tar:
                        res.append([n1,n2,nums[left],nums[right]])
                        while left < right and nums[left] == nums[left + 1]:
                            left += 1
                        while left < right and nums[right] == nums[right - 1]:
                            right -= 1
                        left += 1
                        right -= 1
                    elif s > tar:
                        right -= 1
                    else:
                        left += 1
        return res

```
