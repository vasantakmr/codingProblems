---
title: 'Remove loop in Linked List'
tocTitle: 'Remove loop in Linked List'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/remove-loop-in-linked-list/1)

```clike
void removeLoop(Node* head) {
    int flag = 0;
    Node* slow = head;
    Node* fast = head;
    while(slow && fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
        if(slow == fast) {
            flag = 1;
            break;
        }
    }
    if(slow == fast) {
        slow = head;
        if(slow == fast) {
            while(slow!=fast->next) {
                fast = fast->next; 
            }
        } else {
            while(slow->next != fast->next) {
                slow = slow->next;
                fast = fast->next;
            }
        }
        fast->next = NULL;
    }
}
```