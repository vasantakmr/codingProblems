---
title: 'Trapping Rain Water Problem'
tocTitle: 'Trapping Rain Water'
description: ''
commit: 4211d5e
---

[Problem Link](https://practice.geeksforgeeks.org/problems/trapping-rain-water/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--) {
	    int n;
	    cin>>n;
	    long long int a[n], rarr[n]={0}, larr[n]={0};
	    for(int i=0; i<n; i++) {
	        cin>>a[i];
	    }
	    long long int first, second;
	    first = a[0];
	    second = a[n-1];
	    for(int i=0; i<n; i++) {
	        larr[i] = max(a[i], first);
	        if(a[i]>first) {
	            first = a[i];
	        }
	        rarr[n-i-1] = max(a[n-i-1], second);
	        if(a[n-i-1]>second) {
	            second = a[n-i-1];
	        }
	    }
	    int result=0;
	    for(int i=0; i<n; i++) {
	        result += min(larr[i],rarr[i])- a[i];
	    }
	    cout<<result<<endl;
	}
	return 0;
}
```