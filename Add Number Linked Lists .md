# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given the head of two singly linked lists num1 and num2 representing two non-negative integers. The task is to return the head of the linked list representing the sum of these two numbers.

For example, num1 represented by the linked list : 1 -> 9 -> 0, similarly num2 represented by the linked list: 2 -> 5. Sum of these two numbers is represented by 2 -> 1 -> 5.

Note: There can be leading zeros in the input lists, but there should not be any leading zeros in the output list.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    Node reverse(Node head) {
        Node prev = null, curr = head;
        while (curr != null) {
            Node next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        return prev;
    }

    Node addTwoLists(Node l1, Node l2) {
        l1 = reverse(l1);
        l2 = reverse(l2);
        Node dummy = new Node(0);
        Node tail = dummy;
        int carry = 0;

        while (l1 != null || l2 != null || carry != 0) {
            int sum = carry;
            if (l1 != null) {
                sum += l1.data;
                l1 = l1.next;
            }
            if (l2 != null) {
                sum += l2.data;
                l2 = l2.next;
            }
            carry = sum / 10;
            tail.next = new Node(sum % 10);
            tail = tail.next;
        }

        Node res = reverse(dummy.next);
        while (res != null && res.data == 0 && res.next != null) {
            res = res.next;
        }
        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    Node* reverse(Node* head) {
        Node* prev = nullptr;
        Node* curr = head;
        while (curr) {
            Node* next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
        }
        return prev;
    }

    Node* addTwoLists(Node* l1, Node* l2) {
        l1 = reverse(l1);
        l2 = reverse(l2);
        Node* dummy = new Node(0);
        Node* tail = dummy;
        int carry = 0;

        while (l1 || l2 || carry) {
            int sum = carry;
            if (l1) sum += l1->data, l1 = l1->next;
            if (l2) sum += l2->data, l2 = l2->next;
            carry = sum / 10;
            tail->next = new Node(sum % 10);
            tail = tail->next;
        }

        Node* res = reverse(dummy->next);
        delete dummy;
        while (res && res->data == 0 && res->next) {
            Node* temp = res;
            res = res->next;
            delete temp;
        }
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def reverse(self, head):
        prev, curr = None, head
        while curr:
            next_node = curr.next
            curr.next = prev
            prev = curr
            curr = next_node
        return prev

    def addTwoLists(self, l1, l2):
        l1 = self.reverse(l1)
        l2 = self.reverse(l2)
        dummy = Node(0)
        tail = dummy
        carry = 0

        while l1 or l2 or carry:
            summ = carry
            if l1:
                summ += l1.data
                l1 = l1.next
            if l2:
                summ += l2.data
                l2 = l2.next
            carry = summ // 10
            tail.next = Node(summ % 10)
            tail = tail.next

        res = self.reverse(dummy.next)
        while res and res.data == 0 and res.next:
            res = res.next
        return res
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
