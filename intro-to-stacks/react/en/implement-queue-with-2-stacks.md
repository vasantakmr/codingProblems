---
title: 'Queue using Two Stacks Problem'
tocTitle: 'Queue using Two Stacks'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/queue-using-two-stacks/1)

```clike
void StackQueue :: push(int x)
{
    s1.push(x);
}

int StackQueue :: pop()
{
    if(s2.empty() && s1.empty()) {
        return -1;
    }
    if (s2.empty()) { 
        while (!s1.empty()) { 
            s2.push(s1.top()); 
            s1.pop(); 
        } 
    } 
    int x = s2.top(); 
    s2.pop(); 
    return x; 
}
