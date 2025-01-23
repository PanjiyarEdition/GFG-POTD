# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given a special linked list where each node has two pointers:

A next pointer pointing to the next node.
A random pointer pointing to any random node in the list or NULL.
Your task is to construct a deep copy of the linked list. The copied list should consist of the same number of nodes, and both the next and random pointers in the new list should be correctly set.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    Node cloneLinkedList(Node head) {
        if (head == null) return null;

        for (Node t = head; t != null; t = t.next.next) {
            Node n = new Node(t.data);
            n.next = t.next;
            t.next = n;
        }
        for (Node t = head; t != null; t = t.next.next) {
            if (t.random != null) t.next.random = t.random.next;
        }
        Node newHead = head.next;
        for (Node t = head; t != null; t = t.next) {
            Node temp = t.next;
            t.next = temp.next;
            if (temp.next != null) temp.next = temp.next.next;
        }
        return newHead;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    Node* cloneLinkedList(Node* head) {
        if (!head) return nullptr;
        for (Node* t = head; t; t = t->next->next) {
            Node* n = new Node(t->data);
            n->next = t->next;
            t->next = n;
        }
        for (Node* t = head; t; t = t->next->next)
            if (t->random) t->next->random = t->random->next;
        Node* newHead = head->next;
        for (Node* t = head; t; t = t->next) {
            Node* temp = t->next;
            t->next = temp->next;
            if (temp->next) temp->next = temp->next->next;
        }
        return newHead;
    }
};
```

# Python
``` python []

class Solution:
    def cloneLinkedList(self, head):
        if not head:
            return None

        d = {}
        ch = Node(head.data)
        chh = ch
        d[head] = ch

        h = head.next
        while h:
            nn = Node(h.data)
            chh.next = nn
            d[h] = nn
            h = h.next
            chh = nn

        h = head
        chh = ch
        while h:
            if h.random:
                chh.random = d[h.random]
            h = h.next
            chh = chh.next

        return ch    
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
