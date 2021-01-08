---
title: 'Introduction to design systems'
tocTitle: 'Introduction'
description: ''
---

Import statements for stack:
```clike
#include<stack>
// or
#include<bits/stdc++.h>
```
Declaration of stack:
```cpp
stack<int> stk;
```

```cpp
// Check for balanced paranthesis
bool ispar(string x)
{
    stack<char> stk;
    stk.push('+');
    for(int i=0; i<x.length(); i++) {
        if(x[i]=='{' || x[i]=='[' || x[i]=='(') {
            stk.push(x[i]);
        } else if(x[i]=='}' && stk.top()=='{') {
            stk.pop();
        } else if(x[i]==']' && stk.top()=='[') {
            stk.pop();
        } else if(x[i]==')' && stk.top()=='(') {
            stk.pop();
        } else if(x[i]=='}' && stk.top()!='{') {
            return false;
        } else if(x[i]==')' && stk.top()!='(') {
            return false;
        } else if(x[i]==']' && stk.top()!='[') {
            return false;
        }
    }
    if(stk.top()=='+')
        return true;
    else 
        return false;
}
```

```cpp
// Implement queue using 2 stacks
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
```