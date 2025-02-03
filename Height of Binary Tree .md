# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given a binary tree, find its height.
The height of a tree is defined as the number of edges on the longest path from the root to a leaf node. A leaf node is a node that does not have any children.



# 📝Code ⬇:-


# Java
```java []

class Solution {
    int height(Node node){
        return node == null ? -1 : 1 + Math.max(height(node.left), height(node.right));
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int height(Node* node) {
        return node ? 1 + max(height(node->left), height(node->right)) : -1;
    }
};
```

# Python
``` python []

class Solution:
    def height(self, root):
        return -1 if not root else 1 + max(self.height(root.left), self.height(root.right)) 
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
