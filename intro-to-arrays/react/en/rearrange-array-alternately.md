---
title: 'Rearrange Array Alternately Problem'
tocTitle: 'Rearrange Array Alternately'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/-rearrange-array-alternately/0/)

```clike
#include<bits/stdc++.h>
using namespace std;

void rearrange(long long *arr, int n) { 
	int maxIdx = n-1, minIdx = 0, maxEle = arr[n-1] +1;
	for(int i=0; i<n; i++) {
	    if(i%2){
	        arr[i] = arr[i] + ((arr[minIdx] % maxEle) * maxEle);
	        minIdx++;
	    } else {
	        arr[i] = arr[i] + ((arr[maxIdx] % maxEle) * maxEle);
	        maxIdx--;
	    }
	}
	for(int i=0; i<n; i++) {
	    arr[i] = arr[i] / maxEle;
	}
}

int main() {
    int n; cin>>n;
    int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    rearrange(arr, n);
}
```