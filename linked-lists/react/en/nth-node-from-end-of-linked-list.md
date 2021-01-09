---
title: 'Nth node from end of linked list'
tocTitle: 'Nth node from end of linked list'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/nth-node-from-end-of-linked-list/1)

```clike
int getNthFromLast(Node *head, int n){
    Node* newHead = head; 
    int count=0; 
    while(head) {
        head = head->next;
        count++;
    }
    if(count<n) {
        return -1;
    }
    count = count-n+1;
    while(--count) {
        newHead = newHead->next;
    }
    return newHead->data;
}
```