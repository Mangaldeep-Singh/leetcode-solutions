# Palindrome Number

**Difficulty:** Easy  
**Patterns:** General

🔗 https://leetcode.com/problems/palindrome-number/

---

## 🧠 Intuition
- **General**: We transform the problem to enable efficient grouping or lookup.

---

## ✅ Solution (Python)
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0: return False
        n = 0
        t = x
        while x > 0:
            n = n*10+(x%10)
            x //= 10
        return t == n
        
```
