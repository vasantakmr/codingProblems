---
title: "Kadane's Algorithm Problem"
tocTitle: "Kadane's Algorithm"
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/kadanes-algorithm/0)

```clike
#include<bits/stdc++.h>
using namespace std;

int maxSubarraySum(int arr[], int n){
    int curr_max=0, maxx=INT_MIN;
    for(int i=0; i<n; i++) {
        curr_max += arr[i];
        if(curr_max>maxx) {
            maxx = curr_max;
        } 
        if(curr_max<0) {
            curr_max=0;
        }
    }
    return maxx;
}

int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    cout<<maxSubarraySum(arr, n)<<endl;
}
```