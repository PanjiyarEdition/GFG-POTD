# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given the head of a linked list that may contain a loop.  A loop means that the last node of the linked list is connected back to a node in the same list. The task is to remove the loop from the linked list (if it exists).


# 📝Code ⬇:-



# Java
```java []

CODE HERE

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

CODE HERE     
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
