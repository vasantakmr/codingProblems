---
title: 'Sort an array of 0s, 1s and 2s Problem'
tocTitle: 'Sort array of 0s, 1s and 2s'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/sort-an-array-of-0s-1s-and-2s4231/1)

```clike
#include <bits/stdc++.h>
using namespace std;

void sort012(int a[], int n)
{
    vector<int> arr(3,0);
    for(int i=0; i<n; i++) {
        arr[a[i]]++;
    }
    int count=0;
    for(int i=0; i<3; i++) {
        for(int j=0; j<arr[i]; j++) {
            a[count++] = i;
        }
    } 
}

int main() {
    int n;
    cin>>n;
    int a[n];
    for(int i=0; i<n; i++) {
        cin>>a[i];
    }
    sort012(a, n);
    for(int i=0; i<n; i++) {
        cout<<a[i]<<" ";
    }
    return 0;
}
```