# Group Anagrams

**Difficulty:** Medium  
**Patterns:** Hashing, Stack

🔗 https://leetcode.com/problems/group-anagrams/

---

## 🧠 Intuition
- **Hashing**: We group elements by a computed key using a hashmap for O(1) access.
- **Stack**: A stack keeps only relevant elements while discarding others.

---

## ✅ Solution (Python)
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        if len(strs) == 0: return []
        
        gr_dict = dict()
        for i in strs:
            ch_count = [0] * 26
            for j in i:
                ch_count[ord(j)-97] += 1
                # print(j,ch_count)
            key = '-'.join(map(str,ch_count))
            print(key)
            if key not in gr_dict:
                gr_dict[key] = [i]
            else: gr_dict[key].append(i)
        return list(gr_dict.values())
```
