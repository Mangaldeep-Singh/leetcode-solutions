# Alien Dictionary

**Difficulty:** Medium  
**Topic:** Uncategorized  
**Pattern:** General

🔗 https://leetcode.com/problems/alien-dictionary/description/

---

## 📘 Description
Description not available

---

## 🧠 Intuition
- **General**: We transform the problem to enable efficient grouping or lookup.

---

## ✅ Solution (Python)
```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        maxAr,lwall,rwall = 0,0,len(height) - 1
        while lwall < rwall:
            curAr = (min(height[lwall],height[rwall]) * (rwall - lwall))
            maxAr = max(maxAr, curAr)
            if height[lwall] < height[rwall]:
                lwall += 1
            else:
                rwall -= 1
        return maxAr
```
