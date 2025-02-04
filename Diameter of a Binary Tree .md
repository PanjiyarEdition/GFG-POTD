# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given a binary tree, the diameter (also known as the width) is defined as the number of edges on the longest path between two leaf nodes in the tree. This path may or may not pass through the root. Your task is to find the diameter of the tree.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    int[] f(Node r) {
        if (r == null) return new int[]{0, 0};
        int[] a = f(r.left), b = f(r.right);
        int h = 1 + Math.max(a[0], b[0]);
        int d = Math.max(Math.max(a[1], b[1]), a[0] + b[0]);
        return new int[]{h, d};
    }
    
    int diameter(Node root) {
        return f(root)[1];
    }
}

```

# C++
``` cpp []

class Solution {
  public:
    int dfs(Node* n, int &d) {
        if (!n) return 0;                      // Base case: empty node has height 0
        int l = dfs(n->left, d), r = dfs(n->right, d);
        d = max(d, l + r);                       // Update diameter if path through n is larger
        return 1 + max(l, r);                    // Return height of current node
    }

    int diameter(Node* root) {
        int d = 0;
        dfs(root, d);
        return d;                              // Final diameter
    }
};
```

# Python
``` python []

class Solution:
    def f(self, r):
        if not r: 
            return (0, 0)
        a, b = self.f(r.left), self.f(r.right)
        h = 1 + max(a[0], b[0])
        d = max(a[1], b[1], a[0] + b[0])
        return (h, d)
    
    def diameter(self, root):
        return self.f(root)[1]    
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
