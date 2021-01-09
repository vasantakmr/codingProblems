---
title: 'Find First Set Bit Problem'
tocTitle: 'Find First Set Bit'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/find-first-set-bit/0)


```clike
#include<bits/stdc++.h>
using namespace std;

unsigned int getFirstSetBit(int n){
    unsigned int rem, divisor , count=0;
    while(n) {
        rem = n%2;
        n = n/2;
        count++;
        if(rem == 1) {
            return count;
        }
    }
    return 0;    
}

int main() {
    int n;
    cin>>n;
    cout<<getFirstSetBit(n);
    return 0;
}
```