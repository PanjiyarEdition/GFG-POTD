# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given the head of a linked list, the task is to reverse every k nodes in the linked list. If the number of nodes is not a multiple of k, the left-out nodes at the end should be treated as a group and must also be reversed.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public static Node reverseKGroup(Node head, int k) {
        if (head == null || k <= 1) return head;

        Node curr = head, newHead = null, tail = null;

        while (curr != null) {
            Node groupPrev = null, groupCurr = curr;
            int count = 0;

            while (curr != null && count < k) {
                Node next = curr.next;
                curr.next = groupPrev;
                groupPrev = curr;
                curr = next;
                count++;
            }

            if (newHead == null) newHead = groupPrev;
            if (tail != null) tail.next = groupPrev;
            tail = groupCurr;
        }

        return newHead;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    Node* reverseKGroup(Node* head, int k) {
        if (!head || k <= 1) return head;

        Node* curr = head;
        Node* newHead = nullptr;
        Node* tail = nullptr;

        while (curr) {
            Node* groupPrev = nullptr;
            Node* groupCurr = curr;
            int count = 0;

            while (curr && count < k) {
                Node* next = curr->next;
                curr->next = groupPrev;
                groupPrev = curr;
                curr = next;
                count++;
            }

            if (!newHead) newHead = groupPrev;
            if (tail) tail->next = groupPrev;
            tail = groupCurr;
        }

        return newHead;
    }
};
```

# Python
``` python []

class Solution:
    def reverseKGroup(self, head, k):
        if not head or k <= 1:
            return head
        current = head
        new_head = None
        tail = None
        while current:
            group_prev = None
            group_curr = current
            count = 0
            while current and count < k:
                next_node = current.next
                current.next = group_prev
                group_prev = current
                current = next_node
                count += 1
            if not new_head:
                new_head = group_prev
            if tail:
                tail.next = group_prev
            tail = group_curr
        return new_head 
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
