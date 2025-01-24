# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given the head of a singly linked list. Your task is to determine if the linked list contains a loop. A loop exists in a linked list if the next pointer of the last node points to any other node in the list (including itself), rather than being null.

Custom Input format:
A head of a singly linked list and a pos (1-based index) which denotes the position of the node to which the last node points to. If pos = 0, it means the last node points to null, indicating there is no loop.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public static boolean detectLoop(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            if ((slow = slow.next) == (fast = fast.next.next))
                return true;
        }
        return false;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    bool detectLoop(Node* head) {
        Node *slow = head, *fast = head;
        while (fast && fast->next) {
            if ((slow = slow->next) == (fast = fast->next->next))
                return true;
        }
        return false;
    }
};
```

# Python
``` python []

class Solution:
    def detectLoop(self, head):
        slow, fast = head, head
        while fast and fast.next:
            slow, fast = slow.next, fast.next.next
            if slow == fast:
                return True
        return False  
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
