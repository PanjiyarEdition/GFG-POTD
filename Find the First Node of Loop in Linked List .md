# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given the head of a singly linked list. If a loop exists in the list, return the first node of the loop; otherwise, return NULL.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public static Node findFirstNode(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            if ((slow = slow.next) == (fast = fast.next.next)) {
                for (slow = head; slow != fast; slow = slow.next, fast = fast.next);
                return slow;
            }
        }
        return null;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    Node* findFirstNode(Node* head) {
        Node *slow = head, *fast = head;
        while (fast && fast->next) {
            if ((slow = slow->next) == (fast = fast->next->next)) {
                for (slow = head; slow != fast; slow = slow->next, fast = fast->next);
                return slow;
            }
        }
        return nullptr;
    }
};
```

# Python
``` python []

class Solution:
    def findFirstNode(self, head):
        slow, fast = head, head
        while fast and fast.next:
            slow, fast = slow.next, fast.next.next
            if slow == fast:
                slow = head
                while slow != fast:
                    slow, fast = slow.next, fast.next
                return slow
        return None    
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
