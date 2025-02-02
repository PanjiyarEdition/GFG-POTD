# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given a root of a binary tree with n nodes, the task is to find its level order traversal. Level order traversal of a tree is breadth-first traversal for the tree.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public ArrayList<ArrayList<Integer>> levelOrder(Node root) {
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        if (root == null) return res;
        Queue<Node> q = new LinkedList<>();
        q.add(root);
        while (!q.isEmpty()) {
            ArrayList<Integer> level = new ArrayList<>();
            for (int i = q.size(); i > 0; i--) {
                Node n = q.poll();
                level.add(n.data);
                if (n.left != null) q.add(n.left);
                if (n.right != null) q.add(n.right);
            }
            res.add(level);
        }
        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    vector<vector<int>> levelOrder(Node *root) {
        if (!root) return {};
        queue<Node *> q({root});
        vector<vector<int>> res;
        while (!q.empty()) {
            res.push_back({});
            for (int i = q.size(); i > 0; i--) {
                Node *n = q.front(); q.pop();
                res.back().push_back(n->data);
                if (n->left) q.push(n->left);
                if (n->right) q.push(n->right);
            }
        }
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def levelOrder(self, root):
        if not root: return []
        res, q = [], [root]
        while q:
            res.append([n.data for n in q])
            q = [c for n in q for c in (n.left, n.right) if c]
        return res  
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
