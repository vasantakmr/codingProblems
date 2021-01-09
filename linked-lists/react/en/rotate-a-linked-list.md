---
title: 'Rotate a Linked List'
tocTitle: 'Rotate a Linked List'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/rotate-a-linked-list/1)

```clike
Node* rotate(Node* head, int k)
{
    Node* first = head;
    Node* kthNode = NULL;
    Node* newHead = NULL;
    k--;
    while(k-- && head) {
        head = head->next;
    }
    if(head == NULL) {
        return first;
    }
    kthNode = head;
    while(head->next) {
        head = head->next;
    }
    head->next = first;
    newHead = kthNode->next;
    kthNode->next = NULL;
    return newHead;
}
```