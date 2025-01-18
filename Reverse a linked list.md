# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given the head of a singly linked list. Your task is to reverse the list and return the reversed head.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    Node reverseList(Node head) {
        Node prev = null;
        while (head != null) {
            Node next = head.next;
            head.next = prev;
            prev = head;
            head = next;
        }
        return prev;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    Node* reverseList(Node* head) {
        Node *prev = NULL, *curr = head, *next;
        while (curr) {
            next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
        }
        return prev;
    }
};
```

# Python
``` python []

class Solution:
    def reverseList(self, head):
        prev = None
        while head:
            next = head.next
            head.next = prev
            prev = head
            head = next
        return prev
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
