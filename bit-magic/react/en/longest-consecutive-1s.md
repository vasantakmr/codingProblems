---
title: "Longest Consecutive 1's"
tocTitle: "Longest Consecutive 1's"
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/longest-consecutive-1s/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int maxConsecutiveOnes(int x)
{
    int curr=0, maxx=0, rem;
    while(x) {
        rem = x%2;
        if(rem) {
            curr++;
            cout<<curr<<" curr"<<endl;
        } else {
            curr = 0;
        }
        if(curr>maxx) {
            maxx = max(curr, maxx);
            cout<<maxx<<" maxx"<<endl;
        }
        x = x/2;
    }
    return maxx;
}

int main()
{
    int n;
    cin>>n;
    cout<<maxConsecutiveOnes(n)<<endl; 
    return 0;
}
```