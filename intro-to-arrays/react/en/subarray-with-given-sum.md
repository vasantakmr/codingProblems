---
title: 'Subarray with Given Sum Problem'
tocTitle: 'Subarray with Given Sum'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/subarray-with-given-sum/0)

```clike
#include<bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--) {
	    long long int n, s, current_sum=0, j=0, front=0, flag =0;
	    cin>>n>>s;
	    int arr[n];
	    for(int i=0; i<n; i++) {
	        cin>>arr[i];
	    }
	    for(j=0; j<=n; j++) {
	        while((current_sum>s) && (front<n)) {
	            current_sum -= arr[front];
	            front++;
	        }
	        if(current_sum == s) {
	            flag = 1;
	            cout<<front+1<<" "<<j<<endl;
	            break;
	        }
	        if(j<n) {
	            current_sum += arr[j]; 
	        }
	    }
	    if(flag == 0) {
	        cout<<"-1"<<endl;
	    }
	}
	return 0;
}
```