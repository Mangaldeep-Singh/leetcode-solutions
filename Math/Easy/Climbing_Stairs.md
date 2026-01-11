# Climbing Stairs

**Difficulty:** Easy  
**Topic:** Math  
**Pattern:** Dynamic Programming

🔗 https://leetcode.com/problems/climbing-stairs/

---

## 📘 Description
You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

 
Example 1:

Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps


Example 2:

Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step


 
Constraints:


	1 <= n <= 45

---

## 🧠 Intuition
- **Dynamic Programming**: We solve overlapping subproblems and reuse results.

---

## ✅ Solution (Python)
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        """ ways to climb
        1 -> 1
        2 -> (1,1),2
        3 -> (1,2),(1,1,1),(2,1)
        4 -> (1,1,1,1),(1,2,1),(1,1,2),(2,2)
        5 -> (1,1,1,1,1),(1,1,1,2),(1,1,2,1),(1,2,1,1),(2,1,1,1),(1,2,2),(2,1,2),(2,2,1)

        total steps -> prev steps + curr steps
        """
        prv, nxt = 1, 2
        if n <= 2: return n
        for _ in range(n-2):
            nxt += prv
            prv = nxt - prv
        return nxt
```
