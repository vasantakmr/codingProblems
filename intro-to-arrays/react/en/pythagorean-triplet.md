---
title: 'Pythagorean Triplet in an Array Problem'
tocTitle: 'Pythagorean Triplet'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/pythagorean-triplet/0)

```clike
#include <bits/stdc++.h>
using namespace std;

bool checkTriplet(int arr[], int n) {
    for(int i=0; i<n; i++) {
        arr[i] = arr[i] * arr[i];
    }
    unordered_map<int, int> freq;
    int count =0, sum;
    for(int i=0; i<n; i++) {
        freq[arr[i]]++;
    }
    for(int i=0; i<n; i++) {
        for(int j=i+1; j<n; j++) {
            sum = arr[i]+arr[j];
            if(!(freq.find(sum)==freq.end())) {
                return 1;
            }
        }
    }
    return 0;
}

int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    cout<<checkTriplet(arr, n)<<endl;
}
```