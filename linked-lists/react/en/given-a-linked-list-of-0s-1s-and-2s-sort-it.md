---
title: 'Given a linked list of 0s, 1s and 2s, sort it'
tocTitle: 'Given a linked list of 0s, 1s and 2s, sort it'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/given-a-linked-list-of-0s-1s-and-2s-sort-it/1)

```clike
Node* segregate(Node *head) {
    int arr[3] = {0};
    Node* newHead = head;
    Node* newHead2 = head;
    while(head) {
        arr[head->data]++;
        head = head->next;
    }
    for(int i=0; i<3; i++) {
        for(int j=0; j<arr[i]; j++) {
            newHead->data = i;
            newHead = newHead->next;
        }
    }
    return newHead2;
}
```