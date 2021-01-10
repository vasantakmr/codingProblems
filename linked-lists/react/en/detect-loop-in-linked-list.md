---
title: 'Detect Loop in linked list'
tocTitle: 'Detect Loop in linked list'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/detect-loop-in-linked-list/1)

```clike
bool detectLoop(Node* head){
    Node* slow = head;
    Node* fast = head;
    while(slow && fast &&(fast->next)) {
        slow = slow->next;
        fast = fast->next->next;
        if(slow == fast) {
            return true;
        }
    }
    return false;
}
```