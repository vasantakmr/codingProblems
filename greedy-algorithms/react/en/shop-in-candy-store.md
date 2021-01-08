---
title: 'Shop in Candy Store Problem'
tocTitle: 'Shop in Candy Store'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/shop-in-candy-store/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--) {
	    int n, minCandies, minCost=0, maxCost=0;
	    float k;
	    cin>>n>>k;
	    int arr[n];
	    for(int i=0; i<n; i++) {
	        cin>>arr[i];
	    }
	    sort(arr, arr+n);
	    minCandies = ceil((n)/(k+1));
	    for(int i=0; i<minCandies; i++) {
	        minCost += arr[i];
	        maxCost += arr[n-1-i];
	    }
	    cout<<minCost<<" "<<maxCost<<endl;
	}
	return 0;
}
```