# Longest Substring Without Repeating Characters

**Difficulty:** undefined  
**Patterns:** General

🔗 https://leetcode.com/problems/longest-substring-without-repeating-characters/

---

## ⏱️ Complexity Analysis
- **Time:** O(n)
- **Space:** O(1)

---

## ✅ Solution (Python)
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        length  = 0
        for i in range(len(s)):
            visited = []
            if s[i] not in visited:
                    visited.append(s[i])
                    length = max(len(visited), length)
            for j in range(i+1,len(s)):
                if s[j] not in visited:
                    visited.append(s[j])
                    length = max(len(visited), length)
                else:
                    break

        return length
                
```
