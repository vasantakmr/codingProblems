---
title: 'Reverse a linked list'
tocTitle: 'Reverse a linked list'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/reverse-a-linked-list/1)

```clike
struct Node* reverseList(struct Node *head)
{
    Node* prev= NULL;
    Node* next2;
    Node* curr= head;
    while(curr) {
        next2 = curr->next;
        curr->next = prev;
        prev = curr;
        curr = next2;
    }
    while(prev) {
        cout<<prev->data<<" ";
        prev = prev->next;
    }
}
```