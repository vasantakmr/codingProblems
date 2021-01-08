---
title: 'Chocolate Distribution Problem'
tocTitle: 'Chocolate Distribution Problem'
description: ''
---


[Problem Link](https://practice.geeksforgeeks.org/problems/chocolate-distribution-problem/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--) {
	    long long int n, m, minVal = LONG_MAX, rearIdx;
	    cin>>n;
	    long long int arr[n];
	    for(int i=0; i<n; i++) {
	        cin>>arr[i];
	    }
	    cin>>m;
	    sort(arr, arr+n);
	    rearIdx = m-1;
	    for(int i=0; rearIdx<n; i++) {
	        minVal = min((arr[rearIdx]-arr[i]), minVal);
	        rearIdx++;
	    }
	    cout<<minVal<<endl;
	}
	return 0;
}
```