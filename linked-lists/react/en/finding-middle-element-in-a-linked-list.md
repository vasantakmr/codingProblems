---
title: 'Finding middle element in a linked list'
tocTitle: 'Finding middle element in a linked list'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/finding-middle-element-in-a-linked-list/1)

```clike
int getMiddle(Node *head)
{
   int count=0;
   int mid =0;
   Node* ref = head;
   while(ref) {
       ref = ref->next;
       count++;
   }
   mid = count/2; 
   while(mid--) {
       head = head->next;
   } 
   return head->data;
}
```