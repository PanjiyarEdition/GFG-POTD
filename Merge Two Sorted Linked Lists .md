# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given the head of two sorted linked lists consisting of nodes respectively. The task is to merge both lists and return the head of the sorted merged list.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    Node sortedMerge(Node head1, Node head2) {
        Node dummy = new Node(0), tail = dummy;
        while (head1 != null && head2 != null) {
            tail.next = (head1.data <= head2.data) ? head1 : head2;
            if (head1.data <= head2.data) head1 = head1.next;
            else head2 = head2.next;
            tail = tail.next;
        }
        tail.next = (head1 != null) ? head1 : head2;
        return dummy.next;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    Node* sortedMerge(Node* head1, Node* head2) {
        Node dummy(0), *tail = &dummy;
        while (head1 && head2) {
            tail->next = (head1->data <= head2->data) ? head1 : head2;
            tail = tail->next;
            if (head1->data <= head2->data) head1 = head1->next;
            else head2 = head2->next;
        }
        tail->next = head1 ? head1 : head2;
        return dummy.next;
    }
};
```

# Python
``` python []

class Solution:
    def sortedMerge(self, head1, head2):
        dummy = Node(0)
        tail = dummy
        while head1 and head2:
            if head1.data <= head2.data:
                tail.next = head1
                head1 = head1.next
            else:
                tail.next = head2
                head2 = head2.next
            tail = tail.next
        tail.next = head1 or head2
        return dummy.next  
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
