---
title: 'Minimize the Sum of Product Problem'
tocTitle: 'Minimize Sum of Product'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/minimize-the-sum-of-product/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--) {
	    long long int n, product=0;
	    cin>>n;
	    long long int a[n], b[n];
	    for(int i=0; i<n; i++) {
	        cin>>a[i];
	    }
	    for(int i=0; i<n; i++) {
	        cin>>b[i];
	    }
	    sort(a, a+n);
	    sort(b, b+n);
	    for(int i=0; i<n; i++) {
	        product += (a[i]*b[n-1-i]);
	    }
	    cout<<product<<endl;
	}
	return 0;
}
```