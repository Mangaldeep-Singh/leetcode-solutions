# Container With Most Water

**Difficulty:** Medium  
**Topic:** Array  
**Pattern:** Two Pointers

🔗 https://leetcode.com/problems/container-with-most-water/

---

## 📘 Description
You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.

 

Example 1:

Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.


Example 2:

Input: height = [1,1]
Output: 1


 

Constraints:

n == height.length
2 <= n <= 105
0 <= height[i] <= 104

---

## 🧠 Intuition
- **Two Pointers**: Use this technique to optimize the solution.

---

## ✅ Solution (Python)
```python
class Solution:
    def romanToInt(self, s: str) -> int:
        sum = 0
        ddict = {'M':1000,'D':500,'C':100,'L':50,'X':10,'V':5,'I':1}
        for i in range(len(s)):
            if i > 0 and ddict[s[i]] > ddict[s[i-1]]:
                sum += ddict[s[i]] - 2* ddict[s[i-1]]
            else: sum += ddict[s[i]] 
        return (sum)
```
