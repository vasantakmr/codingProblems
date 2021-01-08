---
title: 'Parenthesis Checker Problem'
tocTitle: 'Parenthesis Checker'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/parenthesis-checker/0)

```clike
bool isValid(string s) {
    stack<char> stk;
    stk.push('+');
    for(int i=0; i<s.length(); i++) {
        if(s[i]==')' && stk.top()!='(') {
            return false;
        } else if(s[i]==']' && stk.top()!='[') {
            return false;
        } else if(s[i]=='}' && stk.top()!='{') {
            return false;
        } else if(s[i]==')' && stk.top()=='(') {
            stk.pop();
        } else if(s[i]==']' && stk.top()=='[') {
            stk.pop();
        } else if(s[i]=='}' && stk.top()=='{') {
            stk.pop();
        } else if(s[i]=='(' || s[i]=='[' || s[i]=='{') {
            stk.push(s[i]);
        } 
    }
    if(stk.top() == '+') {
        return true;
    } else {
        return false;
    }
}
```