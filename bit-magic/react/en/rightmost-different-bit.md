---
title: 'Rightmost Different Bit Problem'
tocTitle: 'Rightmost Different Bit'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/rightmost-different-bit/0)


```clike
#include<bits/stdc++.h>
using namespace std;

int posOfRightMostDiffBit(int m, int n)
{
    int num = m^n;
    int rem, divisor , count=0;
    while(num) {
        rem = num%2;
        num = num/2;
        count++;
        if(rem == 1) {
            return count;
        }
    }
    return -1;    
}

int main() {
    int n, m;
    cin>>n>>m;
    cout<<posOfRightMostDiffBit(n, m);
    return 0;
}
```