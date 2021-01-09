---
title: 'Power of 2 Problem'
tocTitle: 'Power of 2'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/power-of-2/0)

```clike
#include<bits/stdc++.h>
using namespace std;

bool isPowerofTwo(long long n){ 
    long long int i=1;
    while(n>=i) {
        if(i==n) {
            return 1;
        }
        i = i<<1;
    }
    return 0;
}

int main() {
    int n;
    cin>>n;
    cout<<isPowerofTwo(n);
    return 0;
}
```