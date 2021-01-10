---
title: 'Delete without head pointer'
tocTitle: 'Delete without head pointer'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/delete-without-head-pointer/1)

```clike
void deleteNode(Node *node)
{
    Node* nextt;
    Node* nextnext;
    nextt = node->next;
    nextnext = node->next->next;
    node->data = nextt->data;
    node->next = nextnext;
    nextt->next = NULL;
}
```