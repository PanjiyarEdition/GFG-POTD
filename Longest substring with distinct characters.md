# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given a string s, find the length of the longest substring with all distinct characters. 


# 📝Code ⬇:-



# Java
```java []
class Solution {
    public int longestUniqueSubstr(String s) {
        int[] lastSeen = new int[128];
        int maxLength = 0, start = 0;
        for (int end = 0; end < s.length(); end++) {
            start = Math.max(start, lastSeen[s.charAt(end)]);
            lastSeen[s.charAt(end)] = end + 1;
            maxLength = Math.max(maxLength, end - start + 1);
        }
        return maxLength;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int longestUniqueSubstr(string &s) {
        int lastSeen[128] = {}, maxLength = 0, start = 0;
        for (int end = 0; end < s.size(); ++end) {
            start = max(start, lastSeen[s[end]]);
            lastSeen[s[end]] = end + 1;
            maxLength = max(maxLength, end - start + 1);
        }
        return maxLength;
    }
};
```

# Python
``` python []

class Solution:
    def longestUniqueSubstr(self, s):
        last_seen = [-1] * 128  
        max_length = 0
        start = 0

        for end, char in enumerate(s):
            start = max(start, last_seen[ord(char)] + 1)
            last_seen[ord(char)] = end
            max_length = max(max_length, end - start + 1)

        return max_length    
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
