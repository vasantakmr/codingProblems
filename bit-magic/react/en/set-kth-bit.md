---
title: 'Set kth bit'
tocTitle: 'Set kth bit'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/set-kth-bit/0)

```clike
#include<bits/stdc++.h>
using namespace std;

int setKthBit(int n, int k){
    return (1<<k)|n;
}

int main() {
    int n, k;
    cin>>n>>k;
    cout<<setKthBit(n, k);
    return 0;
}
```