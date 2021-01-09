---
title: 'Number of Paths Problem'
tocTitle: 'Number of Paths'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/number-of-paths/0)

```clike
#include<bits/stdc++.h>
using namespace std;

long long numberOfPaths(int m, int n)
{
    if(m==1 || n==1)
        return 1;
    
    return numberOfPaths(n-1, m) + numberOfPaths(n, m-1);
}

int main() {
    int m, n;
    cin>>m>>n;
    cout<<numberOfPaths(m,n);
    return 0;
}