---
title: 'Missing Number in Array Problem'
tocTitle: 'Missing Number in Array'
---

[Problem Link](https://practice.geeksforgeeks.org/problems/missing-number-in-array1416/1)

```clike
#include <bits/stdc++.h>
using namespace std;

int MissingNumber(vector<int>& array, int n) {
    int total=0;
    for(int i=1; i<=n-1; i++) {
        total += i;
        total -= array[i-1];
    }
    total += n;
    return total;
}

int main() {
    int n, temp;
    cin>>n;
    vector<int> array;
    for(int i=0; i<(n-1); i++) {
        cin>>temp;
        array.push_back(temp);
    }
    cout<<MissingNumber(array, n)<<endl;
    return 0;
}
```