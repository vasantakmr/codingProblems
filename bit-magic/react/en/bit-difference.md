---
title: 'Bit Difference Problem'
tocTitle: 'Bit Difference'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/bit-difference/0)

```clike
#include<bits/stdc++.h>
using namespace std;

int countBitsFlip(int a, int b){
    int count=0, temp=1;
    int num = a^b;
    while(num) {
        if(temp&num) {
            count++;
        }
        num = num/2;
    }
    return count;
}

int main() {
    int a, b;
    cin>>a>>b;
    cout<<countBitsFlip(a, b);
    return 0;
}
```