---
title: 'Last Index of 1 Problem'
tocTitle: 'Last Index of 1'
description: ''
---


[Problem Link](https://practice.geeksforgeeks.org/problems/last-index-of-1/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int main() {
	//code
	int t;
	cin>>t;
	while(t--) {
	    int ans, len, flag = 0;
	    string s;
	    cin>>s;
	    len = s.length();
	    while(len--) {
            if(s[len]=='1') {
                cout<<len<<endl;
                flag = 1;
                break;
            }
	    }
	    if(flag == 0) {
	        cout<<"-1"<<endl;   
	    }
	}
	return 0;
}
```