---
title: 'Coin Piles Problem'
tocTitle: 'Coin Piles'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/coin-piles/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--) {
	    int n, k, count=0, temp=0, ans = INT_MAX;
	    cin>>n>>k;
	    int arr[n];
	    for(int i=0; i<n; i++) {
	        cin>>arr[i];
	    }
	    sort(arr, arr+n);
	    int minValue = arr[0];
	    for(int j=0; j<n; j++) {
	        count = temp;
	        temp += arr[j];
	        for(int i=n-1; i>j; i--) {
	            if((arr[i]-arr[j])>k) {
	                count += (arr[i]-arr[j]-k);
	            } else {
	                break;
	            }
	        }
	        ans = min(count, ans);
	    }
	    cout<<ans<<endl;
	}
	return 0;
}
```