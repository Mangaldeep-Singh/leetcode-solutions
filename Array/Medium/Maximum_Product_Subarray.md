# Maximum Product Subarray

**Difficulty:** Medium  
**Topic:** Array  
**Pattern:** Dynamic Programming

🔗 https://leetcode.com/problems/maximum-product-subarray/

---

## 📘 Description
Given an integer array nums, find a subarray that has the largest product, and return the product.

The test cases are generated so that the answer will fit in a 32-bit integer.

Note that the product of an array with a single element is the value of that element.

 
Example 1:

Input: nums = [2,3,-2,4]
Output: 6
Explanation: [2,3] has the largest product 6.


Example 2:

Input: nums = [-2,0,-1]
Output: 0
Explanation: The result cannot be 2, because [-2,-1] is not a subarray.


 
Constraints:


	1 <= nums.length <= 2 * 104
	-10 <= nums[i] <= 10
	The product of any subarray of nums is guaranteed to fit in a 32-bit integer.

---

## 🧠 Intuition
- **Dynamic Programming**: We solve overlapping subproblems and reuse results.

---

## ✅ Solution (Python)
```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        maxpr =minpr= nums[0]
        res = maxpr
        curpr = nums[0]
        for i in range(1,len(nums)):
            curpr = nums[i]
            # curpr = max(i,curpr)
            temp = max(maxpr*curpr,curpr,minpr*curpr)
            minpr = min(maxpr*curpr,curpr,minpr*curpr)
            maxpr = temp
            res = max(maxpr,res)
            print(maxpr)
            
        return res
```
