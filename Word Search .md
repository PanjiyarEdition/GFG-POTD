# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given a two-dimensional mat[][] of size n*m containing English alphabets and a string word. Check if the word exists on the mat. The word can be constructed by using letters from adjacent cells, either horizontally or vertically. The same cell cannot be used more than once.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public boolean isWordExist(char[][] b, String w) {
        for (int i = 0; i < b.length; i++)
            for (int j = 0; j < b[0].length; j++)
                if (b[i][j] == w.charAt(0) && dfs(b, w, i, j, 0))
                    return true;
        return false;
    }

    private boolean dfs(char[][] b, String w, int i, int j, int k) {
        if (k == w.length()) return true;
        if (i < 0 || j < 0 || i >= b.length || j >= b[0].length || b[i][j] != w.charAt(k)) return false;
        char t = b[i][j];
        b[i][j] = '#';
        boolean f = dfs(b, w, i - 1, j, k + 1) || dfs(b, w, i + 1, j, k + 1) ||
                   dfs(b, w, i, j - 1, k + 1) || dfs(b, w, i, j + 1, k + 1);
        b[i][j] = t;
        return f;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    bool dfs(vector<vector<char>> &b, string &w, int i, int j, int k) {
        if(k == w.size()) return true;
        if(i < 0 || j < 0 || i >= b.size() || j >= b[0].size() || b[i][j] != w[k]) return false;
        char t = b[i][j]; 
        b[i][j] = '#';
        bool f = dfs(b, w, i-1, j, k+1) || dfs(b, w, i+1, j, k+1) ||
                 dfs(b, w, i, j-1, k+1) || dfs(b, w, i, j+1, k+1);
        b[i][j] = t;
        return f;
    }
    
    bool isWordExist(vector<vector<char>> &b, string w) {
        for(int i = 0; i < b.size(); i++)
            for(int j = 0; j < b[0].size(); j++)
                if(b[i][j] == w[0] && dfs(b, w, i, j, 0))
                    return true;
        return false;
    }
};
```

# Python
``` python []

class Solution:
    def isWordExist(self, b, w):
        def dfs(i, j, k):
            if k == len(w): return True
            if i < 0 or j < 0 or i >= len(b) or j >= len(b[0]) or b[i][j] != w[k]: return False
            t, b[i][j] = b[i][j], '#'
            f = any(dfs(i + dx, j + dy, k + 1) for dx, dy in [(-1, 0), (1, 0), (0, -1), (0, 1)])
            b[i][j] = t
            return f

        return any(dfs(i, j, 0) for i in range(len(b)) for j in range(len(b[0])) if b[i][j] == w[0])
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
