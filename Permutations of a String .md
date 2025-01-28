# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given a string s, which may contain duplicate characters, your task is to generate and return an array of all unique permutations of the string. You can return your answer in any order.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public ArrayList<String> findPermutation(String s) {
        ArrayList<String> res = new ArrayList<>();
        char[] chars = s.toCharArray();
        Arrays.sort(chars);
        do res.add(new String(chars));
        while (next(chars));
        return res;
    }

    private boolean next(char[] c) {
        int i = c.length - 2, j = c.length - 1;
        while (i >= 0 && c[i] >= c[i + 1]) i--;
        if (i < 0) return false;
        while (c[j] <= c[i]) j--;
        char t = c[i]; c[i] = c[j]; c[j] = t;
        for (int l = i + 1, r = c.length - 1; l < r; l++, r--) {
            t = c[l]; c[l] = c[r]; c[r] = t;
        }
        return true;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    vector<string> findPermutation(string s) {
        vector<string> res;
        sort(s.begin(), s.end());
        do {
            res.push_back(s);
        } while (next_permutation(s.begin(), s.end()));
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def findPermutation(self, s):
        s, res = ''.join(sorted(s)), []
        while s:
            res.append(s)
            s = self.next(s)
        return res

    def next(self, s):
        s = list(s)
        i = len(s) - 2
        while i >= 0 and s[i] >= s[i + 1]: i -= 1
        if i < 0: return None
        j = len(s) - 1
        while s[j] <= s[i]: j -= 1
        s[i], s[j] = s[j], s[i]
        return ''.join(s[:i + 1] + s[i + 1:][::-1])   
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
