# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given the head of a singly linked list and an integer k. Your task is to left-rotate the linked list k times.


# 📝Code ⬇:-



# Java
```java []

class Solution {
  public Node rotate(Node head, int k) {
    if (head == null || head.next == null || k == 0) return head;
    int len = 1;
    Node tail = head;
    while (tail.next != null) {
      tail = tail.next;
      len++;
    }
    k %= len;
    if (k == 0) return head;
    Node newTail = head;
    for (int i = 1; i < k; i++) {
      newTail = newTail.next;
    }
    Node newHead = newTail.next;
    newTail.next = null;
    tail.next = head;
    return newHead;
  }
}

```

# C++
``` cpp []

class Solution {
 public:
  Node* rotate(Node* head, int k) {
    if (!head || !head->next || !k) return head;
    int len = 1;
    Node* tail = head;
    while (tail->next) tail = tail->next, len++;
    k %= len;
    if (!k) return head;
    Node* newTail = head;
    for (int i = 1; i < k; i++) newTail = newTail->next;
    Node* newHead = newTail->next;
    newTail->next = nullptr;
    tail->next = head;
    return newHead;
  }
};
```

# Python
``` python []

class Solution:
    def rotate(self, head, k):
        if k == 0 or head is None:
            return head
        curr = head
        length = 1
        while curr.next is not None:
            curr = curr.next
            length += 1
        k %= length
        if k == 0:
            curr.next = None
            return head
        curr.next = head
        curr = head
        for _ in range(1, k):
            curr = curr.next
        newHead = curr.next
        curr.next = None
        return newHead
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
