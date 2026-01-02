# Container With Most Water

**Difficulty:** Easy  
**Topics:** Math  
**Patterns:** General

🔗 https://leetcode.com/problems/container-with-most-water/

## ✅ Solution
```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        maxA,lwall,rwall = 0,0,len(height) - 1 
        while(rwall > lwall):
            maxA = max((min(height[lwall],height[rwall])*(rwall - lwall)),maxA)
            if height[rwall] < height[lwall]:
                rwall -= 1
            else:
                lwall += 1
        return maxA
```
