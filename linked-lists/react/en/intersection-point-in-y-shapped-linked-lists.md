---
title: 'Intersection Point in Y Shapped Linked Lists Problem'
tocTitle: 'Intersection Point in Y Shapped Linked Lists'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/intersection-point-in-y-shapped-linked-lists/1)

```clike
int intersectPoint(Node* head1, Node* head2)
{
    int len1=0, len2=0, len;
    Node* temp1 = head1;
    Node* temp2 = head2;
    Node* head;
    while(temp1) {
        len1++;
        temp1 = temp1->next; 
    }
    while(temp2) {
        len2++;
        temp2 = temp2->next;
    }
    len = abs(len2-len1);
    if(len1 > len2) {
        head = head1;
    } else if(len1 < len2) {
        head = head2;
    }
    while(len--) {
        head = head->next;
    }
    if(len1 > len2) {
        head1 = head;
    } else if(len1 < len2) {
        head2 = head;
    }
    while(head1 && head2) {
        if(head1 == head2) {
            return head1->data;
        } else {
            head1 = head1->next;
            head2 = head2->next;
        }
    }
    return -1;    
}
```