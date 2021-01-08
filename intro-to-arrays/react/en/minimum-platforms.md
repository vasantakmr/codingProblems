---
title: 'Minimum Platforms Problem'
tocTitle: 'Minimum Platforms'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/minimum-platforms-1587115620/1)

```clike
#include <bits/stdc++.h>
using namespace std;

int findPlatform(int arr[], int dep[], int n)
{
	sort(arr, arr+n);
	sort(dep, dep+n);
	int platforms=0, ans=-1, i=0, j=0;
	while((i<n) && (j<n)) {
	    if(arr[i]<=dep[j]) {
	        platforms++;
	        i++;
	        ans = max(ans, platforms);
	    } else if(arr[i]>dep[j]) {
	        platforms--;
	        j++;
	    }
	}
	return ans;
}

int main()
{
   int n;
   cin>>n;
   int arr[n], dep[n];
   for(int i=0; i<n; i++) {
       cin>>arr[i];
   }
   for(int i=0; i<n; i++) {
       cin>>dep[i];
   }
   cout<<findPlatform(arr, dep, n)<<endl; 
   return 0;
}
```