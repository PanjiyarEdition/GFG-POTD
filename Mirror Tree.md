# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given a binary tree, convert the binary tree to its Mirror tree.

Mirror of a Binary Tree T is another Binary Tree M(T) with left and right children of all non-leaf nodes interchanged.  


# 📝Code ⬇:-



# Java
```java []

class Solution {
    void mirror(Node node) {
        if (node == null) return;
        mirror(node.left);
        mirror(node.right);
        Node temp = node.left;
        node.left = node.right;
        node.right = temp;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    void mirror(Node* node) {
        if (!node) return;
        mirror(node->left);
        mirror(node->right);
        swap(node->left, node->right);
    }
};
```

# Python
``` python []

class Solution:
    def mirror(self, root):
        if not root:
            return
        self.mirror(root.left)
        self.mirror(root.right)
        root.left, root.right = root.right, root.left   
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
