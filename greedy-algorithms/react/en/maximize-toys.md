---
title: 'Maximize Toys Problem'
tocTitle: 'Maximize Toys'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/maximize-toys/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, k, count = 0, sum = 0;
    cin>>n>>k;
    int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    sort(arr, arr+n);
    for(int i=0; i<n; i++) {
        sum += arr[i];
        if(sum<=k) {
            count++;
        }
    }
    cout<<count<<endl;
    return 0;
}
```