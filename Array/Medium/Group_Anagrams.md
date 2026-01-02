# Group Anagrams

**Difficulty:** Medium  
**Topic:** Array  
**Pattern:** Hash Table

🔗 https://leetcode.com/problems/group-anagrams/

---

## 📘 Description
Given an array of strings strs, group the anagrams together. You can return the answer in any order.

 
Example 1:


Input: strs = ["eat","tea","tan","ate","nat","bat"]

Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

Explanation:


	There is no string in strs that can be rearranged to form "bat".
	The strings "nat" and "tan" are anagrams as they can be rearranged to form each other.
	The strings "ate", "eat", and "tea" are anagrams as they can be rearranged to form each other.



Example 2:


Input: strs = [""]

Output: [[""]]


Example 3:


Input: strs = ["a"]

Output: [["a"]]


 
Constraints:


	1 <= strs.length <= 104
	0 <= strs[i].length <= 100
	strs[i] consists of lowercase English letters.

---

## 🧠 Intuition
- **Hash Table**: Use this technique to optimize the solution.

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
