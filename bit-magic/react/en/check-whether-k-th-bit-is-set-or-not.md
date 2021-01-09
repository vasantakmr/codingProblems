---
title: 'Check whether K-th bit is set or not'
tocTitle: 'Check whether K-th bit is set or not'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/check-whether-k-th-bit-is-set-or-not/0)

```clike
#include<bits/stdc++.h>
using namespace std;

bool checkKthBit(int n, int k){
    return (1<<k)&n? 1: 0;
}

int main() {
    int n, k;
    cin>>n>>k;
    cout<<checkKthBit(n, k);
    return 0;
}
```