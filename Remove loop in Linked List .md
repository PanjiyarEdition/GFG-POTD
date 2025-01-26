# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given the head of a linked list that may contain a loop.  A loop means that the last node of the linked list is connected back to a node in the same list. The task is to remove the loop from the linked list (if it exists).


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public static void removeLoop(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null && (slow = slow.next) != (fast = fast.next.next));
        if (fast == null || fast.next == null) return;
        for (slow = head; slow != fast; slow = slow.next, fast = fast.next);
        while (fast.next != slow) fast = fast.next;
        fast.next = null;
    }
}

```

# C++
``` cpp []

class Solution {
  public:
    void removeLoop(Node* head) {
        //CodeGenius
        Node *slow=head , *fast=head;
        while(fast && fast->next){
            slow=slow->next;
            fast=fast->next->next;
            if(slow==fast) break;
        }
        if(!fast || !fast->next) return;
        
        slow=head;
        while(slow!=fast){
            slow=slow->next;
            fast=fast->next;
        }
        while(slow->next !=fast){
            slow=slow->next;
        }
        slow->next=NULL;
    }
};
```

# Python
``` python []

class Solution:
    def removeLoop(self, head):
        slow, fast = head, head
        while fast and fast.next and (slow := slow.next) != (fast := fast.next.next): pass
        if not fast or not fast.next: return
        slow = head
        while slow != fast: slow, fast = slow.next, fast.next
        while fast.next != slow: fast = fast.next
        fast.next = None   
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
